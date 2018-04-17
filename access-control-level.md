---
layout: guideline
status: draft
title: "Access Control Level"
---

In Ethereum, the concept of the Access Control Level (ACL) is paramount to creating effective smart contracts.
Certain methods may be in control of valuable assets such as the ability to mint new tokens,
or control access to funds in a multi-sig wallet.
Since Ethereum is a public network, anyone would have access to methods, so adding access restriction
is the only means to prevent modifications to assets people shouldn't have control over.

```
require( msg.sender == owner )
```

```
require( balances[msg.sender] >= _amount )
balances[msg.sender] 
```

Describe more in detail below...
