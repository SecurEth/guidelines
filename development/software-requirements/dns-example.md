# DNS Example



### Requirements Specification {#docs-internal-guid-9d3cc77f-0456-331f-7125-1385d39651a5}

\(derived from SDD/Goals\):

1. The DNS contract shall allow any user to register a name that has not already been registered to another owner. \(sha256\[:3\] is c84d\)
2. The DNS contract shall reject any request to register a name that is already registered to another user. \(sha256\[:3\] is 35a4\)
3. The DNS contract shall allow the owner of a domain to change the resolved address. \(sha256\[:3\] is e532\)
4. The DNS contract shall allow anyone to perform a lookup of a registered domain’s resolved address. \(sha256\[:3\] is fffc\)

### Implementation: {#docs-internal-guid-bc5fbce9-0457-3f17-6421-28ed7079afd5}

1  /\*\* @title DNS Registrar \*/

2  contract DNS {

3      // Store the owner of a particular domain

4      mapping\(string =&gt; address\) public domainOwner;

5      // Store the resolution of a particular domain

6      /// @req fffc \`public\` provides access method for domain resolver

7      mapping\(string =&gt; address\) public domainResolution;

8

9      /\*\* @title setDomainResolution Allows user to set resolution for address

10       \* @param \_domain Domain name as ASCII string

11       \* @param \_resolution Address domain will resolve to

12       \*/

13     function setDomainResolution\(

14         string \_domain,

15         address \_resolution

16     \)

17         public

18     {

19         /// @req c84d Check if name has been previously registered

20         if \(domainOwner\[\_domain\] != 0x0\)

21         {

22             /// @req 35a4 Reject if domain has been registered to another user

23             require\(domainOwner\[\_domain\] == msg.sender\);

24         }

25         else // domain owner is unset for this domain

26         {

27             /// @req c84d Keep track of newly registered domain

30             domainOwner\[\_domain\] = msg.sender;

31         }

32         /// @req c84d Allow user to set resolution for newly registered domain

33         /// @req e532 Allow user to change resolution for a domain they own

34         domainResolution\[\_domain\] = \_resolution;

35     }

36 }

