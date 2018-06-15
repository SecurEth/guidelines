# DNS Example

## Requirements Specification {#docs-internal-guid-9d3cc77f-0456-331f-7125-1385d39651a5}

\(derived from SDD/Goals\):

1. The DNS contract shall allow any user to register a name that has not already been registered to another owner. \(`sha256[:3]` is c84d\)
2. The DNS contract shall reject any request to register a name that is already registered to another user. \(`sha256[:3]` is 35a4\)
3. The DNS contract shall allow the owner of a domain to change the resolved address. \(`sha256[:3]` is e532\)
4. The DNS contract shall allow anyone to perform a lookup of a registered domain’s resolved address. \(`sha256[:3]` is fffc\)

## Implementation: {#docs-internal-guid-bc5fbce9-0457-3f17-6421-28ed7079afd5}

{% code-tabs %}
{% code-tabs-item title="DNS.sol" %}
```javascript
/** @title DNS Registrar */
contract DNS {
   // Store the owner of a particular domain
   mapping(string => address) public domainOwner;

   // Store the resolution of a particular domain
   /// @imp fffc `public` provides access method for domain resolver
   mapping(string => address) public domainResolution;

   /** @title setDomainResolution Allows user to set resolution for address
     * @param _domain Domain name as ASCII string
     * @param _resolution Address domain will resolve to
     */
   function setDomainResolution(
     string _domain,
     address _resolution
   )
     public
   {
     /// @imp c84d Check if name has been previously registered
     if (domainOwner[_domain] != 0x0)
     {
        /// @imp 35a4 Reject if domain has been registered to another user
        require(domainOwner[_domain] == msg.sender);
     }
     else // domain owner is unset for this domain
     {
        /// @imp c84d Keep track of newly registered domain
        domainOwner[_domain] = msg.sender;
     }

     /// @imp c84d Allow user to set resolution for newly registered domain
     /// @imp e532 Allow user to change resolution for a domain they own
     domainResolution[_domain] = _resolution;
   }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

