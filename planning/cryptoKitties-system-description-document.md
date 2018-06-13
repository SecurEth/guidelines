# CryptoKitties System Description Document
The Top Level of the CryptoKitties System is at the Users’ perspective.
The user sees the website connected with MetaMask.
From this he can bid on a kittie, breed it or sell it using the Ethereum in his wallet.  

The kitties themselves are cute pictures of unique ERC 721 tokens which make them digital collectables.
Each token is unique or non-fungible.
The tokens can be traded, bought or sold without an intermediary.
Transactions use sliding scale auctions where a top and bottom price are defined.
The price slides from the top to the bottom over a period of a few days.
The buyer can purchase at their preferred price on this scale (as long as no one has purchased it before him).
Two tokens can be combined or bred to create a new token, which is based on the unique characteristics of the parent tokens.
Thus a new baby token is created using the genetics of their parents.

The Crypto Kitties System uses a web interface that interacts with the blockchain via MetaMask.
The Cryptokitties site uses a centralized web server for some interactions,
such drawing the kittie pictures from the metadata of the ERC721 token. 
The blockchain is used for the sliding scale auctions and the transfer of tokens.
Value of the tokens will vary from $3 to $100,000. 

For smart contracts there are 
* sliding scale auction smart contract where when a buyer is found the token changes owners.  
Hundreds of these auctions could take place in parallel
* create ERC721 tokens (for new kitties) and 
* breed Kitties contract.  This contract takes two ERC721 metadata pieces and returns the ERC721 token which becomes 
the property of one owner

 
