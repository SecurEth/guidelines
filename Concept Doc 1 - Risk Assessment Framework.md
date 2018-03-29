SMART CONTRACT DEVELOPMENT GUIDELINES


Concept Document:                  1


Date                                18 Mar 2018


Author:                                Rex Hygate


Title:                                Risk Assessment Framework for Smart Contract Systems


Status:                                Open for Discussion


Overview


The core of this guideline is a model of understanding risk inherent to software development items for Smart Contract Systems. We will leverage the OWASP model, a common framework in software security, to develop this model.


The OWASP model specifies that Risk = Likelihood x Impact. In order to quantify an identified risk and communicate it to interested parties, it is necessary to quantify the Likelihood that an issue with occur and the Impact it will have on the platform or network.


We will perform this analysis at the method level of each smart contract, which will provide a comprehensive analysis of all the possible calls.
  

Figure 1: OWASP Model


Specifically, we define Likelihood as the access control level (ACL) of a given method, and Impact as the ability of that method to affect the use or ownership of valuable assets held in the state of Ethereum or otherwise block their intended use.


Once the level of risk is understood, a level of rigor needed to verify the software can be objectively determined, which is defined as the Design Assurance Level (DAL). The DAL can require a variety of techniques to verify software development items (including testing, simulation, formal verification, etc.) as well as the level of documentation required to be able to conclusively determine adequate testing has been performed.


Purpose


This guideline will define the Design Assurance Levels (DAL) for Ethereum Smart Contract development.  It will define the number and names for the DAL’s.  Most importantly, it will define in Solidity the characteristics of each DAL.  This will be defined clearly, with examples. Finally, the characteristics included will be defined as a set of tool requirements. This will include a standard comment set that will allow definition of the method as a specific DAL level.  


Inputs
        Non required


Outputs


1. Definition of the number and names for the DAL’s.
2. Definition of the characteristics of each DAL (in Solidity)
3. Example of each kind of DAL in Solidity
4. Define the standard comment ”eg: /* Level A !! */”  to define a method as each DAL
5. Define tool requirements enabling automation of this definition.


Plan


To be defined