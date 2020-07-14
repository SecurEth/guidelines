# Risk Assessment

In order to communicate on severity, a common model of risk inherent to smart contract issues discovered is required.
We will leverage the OWASP model, a common framework in software security, to develop this model.

The OWASP model specifies that `Risk = Likelihood x Impact`. In order to quantify an identified risk
and communicate it to interested parties, it is necessary to quantify the Likelihood that an issue with occur
and the Impact it will have on the platform or network.

We will perform this analysis at the method level of each smart contract, which will provide
a comprehensive analysis of all the possible calls.
  
![](../.gitbook/assets/risk_levels.png)

Specifically, we define Likelihood as the access control level (ACL) of a given method,
and Impact as the ability of that method to affect the use or ownership of valuable assets
held in the state of Ethereum or otherwise block their intended use.

Understanding the risk inherent in the different functional components of your smart contract system
is the first step towards performing an assessment on whether a fix is required or can be deferred.
