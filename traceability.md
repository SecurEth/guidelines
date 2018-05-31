---
layout: guideline
status: draft
title: "Traceability"
---

## Why is it important?

Traceability creates a full picture of how you arrived at the decisions you've
made to derive requirements from your goals and put them into action by writing software.
This creates a clear picture for yourself and others to understand your software system.
You can clearly see which requirements meet which goals, which software meets which requirements,
and which tests verify which pieces of software without having to trace it manually.
By creating a report of this tracability, others can clearly see your thought process,
which means they will spend less time reconstructing it themselves and more time giving you feedback.

## How do I do it?

Traceability can be created in a number of ways, all of which can be valid for projects of different sizes.
It is more important that whatever process you go through addresses the problems traceability solves.

In-line comments are one way to do this. Imagine you are writing a contract with one goal: "It must do X, Y, and Z".
In your contract, you could state this at the top of the file, and then you break that down into 3 requirements,
because you figured out you can implement each of X, Y, and Z separately.

```python
"""
# Goal:
This contract must do X, Y, and Z.

# Requirements:
@req 1 Do X
@req 2 Do Y
@req 3 Do Z
"""

# implementation below...
```

Here, we use the `@req` tag, which is a docstring-compatible tag that refers to a requirement.
We don't have a lot of them, so we marked them 1, 2, and 3.

Now we start writing software. In my code, I am implementing each of these requirements in several places.
X might be implemented entirely in 1 method, but Y is not, and Z isn't etiher.

```python
def doX(a: uint256, b: uint256) -> uint256:
    # @req 1 does X here
    return a + b
    
def doSomething():
    # @req 2 does part of Y here
    self.state = 0
    # @req 3 does part of Z here
    transfer(msg.sender, this.balance)
    
def doSomethingElse():
    # @req 2 does the other part of Y here
    self.state += 1
    
@payable
def acceptPayment():
    # @req 3 does the last part of Z here
    assert self.state < 10
```

It is starting to sound complicated, but now I can make a simple table that tells me where everything is:

| Req ID | Method(s) |
| --- | --- |
| 1 | `doX()` |
| 2 | `doSomething()`, `doSomethingElse()` |
| 3 | `doSomething()`, `acceptPayment()` |

I can do the same thing for testing:

```python
def test_X(contract):
    contract.doX(1, 2)  # @req 1

def test_Y(contract):
    contract.doSomething()  # @req 2
    contract.doSomethingElse()  # @req 2

def test_Z(contract):
    contract.acceptPayment()  # @req 3
    contract.doSomethingElse()  # @req 3
```

And I can create a table for this too:

| Req ID | Method(s) | Test(s) |
| --- | --- | --- |
| 1 | `doX()` | `test_X` |
| 2 | `doSomething()`, `doSomethingElse()` | `test_Y` |
| 3 | `doSomething()`, `acceptPayment()` | `test_Z` |

When this really comes in handy is if I have a problem and I need to make a change.
Let's say we figure out we need to modify `Y`.
That means requirement 2 must change, therefore I should update either `doSomething()`
or `doSomethingElse()`, and retest it using `test_Y`.
That's a lot easier to do with this table then if I figured it out myself.

Now let's say we get this code audited and they find a problem with the implementation of `doX()`.
I make the updates and I know that `test_X` is the test I should look at to make sure I am accounting
for whatever corner cases that exist which allowed the security bug.

## Different scales of need

This example works great for a smaller project, with 10 or less requirements, but it doesn't scale
very well to larger projects with many requirements or multiple teams of people working on the same components.

In those scenarios, changes are happening much more often, and with multiple people comes a higher liklihood that
a change does not get communicated, or simply that our numbering scheme doesn't scale well.
It will probably be easier to handle a larger project with many inter-operating smart contracts to have a single
document that specifies the Goals and the Requirements that will implement them.
Your file header would then become a separate document, which makes it clearer what the full story is
in regards to how your Requirements meet your Goals.

Now your documentation is separate from your code, and this could create a scenario where changes get lost.
We recommend that you adopt a system that accounts for changes and a process for verifying updates are
well-communicated and handled accordingly across the codebase.
One way to acheive that is by changing our numbering scheme to a hash-based scheme for our requirement identifiers
We use the first 2 bytes of the SHA-256 hash as follows
(you might need more bytes for a larger set of requirements to protect against collisions):


```markdown
# Goal:
This contract must do X, Y, and Z.

# Requirements:
@req FCF7  Do X
@req 3D45  Do Y
@req 3380  Do Z
```

Our table now looks like this:

| Req ID | Method(s) | Test(s) |
| --- | --- | --- |
| FCF7 | `doX()` | `test_X` |
| 3D45 | `doSomething()`, `doSomethingElse()` | `test_Y` |
| 3380 | `doSomething()`, `acceptPayment()` | `test_Z` |

In this system, if we decided that requirement `FCF7` doesn't fully encompass what it needs to,
we might change that to "Do W and X".
However, in doing this, the hash is updated to `4FE9`.
Well, all our tests and implementations still say `FCF7` which is no longer a valid requirement ID,
so we have to go through and make sure we update all the places it was referenced and validate that
the statements we were making are still valid.
This forces us to reconcile changes as they happen, and ensures that all changes are well-communicated
to the team, otherwise the report will break and the traceability will be incomplete.
