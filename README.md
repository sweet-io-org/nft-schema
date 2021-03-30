## Sweet NFT Design and Schemas

[Sweet](https://sweet.io) Non-Fungible Tokens (NFTs) are representations of Digital Collectibles, stored on public blockchains. 
The information stored on-chain consists only of a URI, and a SHA-256 hash of the contents represented by the URI.
For example, the NFT may represent a simple JPEG.  In this case, the document pointed to by the NFT should contain
a description of the collectible, and a link to the JPEG, along with a SHA-256 hash of the JPEG to confirm its 
authenticity.  

We have published a JSON Schema for documents describing NFTs, with provision for copyright notices, terms and conditions,
and a chain of authenticity for all digital assets needed to represent the token.  

### Chain of Authenticity

The owner of an NFT needs to be able to demonstrate any rights they may be granted over digital assets associated 
with the NFT.  This starts with incorporation of the SHA-256 hash of the token document in the blockchain definition 
of the NFT.  That document should contain SHA-256 hashes of all linked-to resources, including images, videos, 
and other media files.  This allows the possessor of an NFT to confirm that a specific JPEG is associated with that 
NFT.  This chain of authenticity supports preservation of the digital collectible and its associated assets.

### Permanence of the NFT

Sweet chooses to host the NFT document and digital assets on a public CDN, to facilitate sharing and display of the
NFT.  The rights information incorporated in the document may grant the user the ability to make copies of the 
digital assets.  In this situation, the Chain of Authenticity allows the NFT owner or anyone else to confirm that the 
copies are associated with the NFT.  It is therefore critical that all components of the NFT document contain hashes, to
allow confirmation of the association.

### Schemas

We have provided three core schemas, with links below to their latest edition.

* [Token version 1.0](./collectibles/token-1.0.json), an individually numbered collectible, and member of a Series.  Immutable.
* [Series version 1.0](./collectibles/series-1.0.json), description of a series of Tokens.  Immutable.
* [Set 1.0](./collectibles/set-1.0.json), a collection of Series.  This is a mutable definition.


Copyright (c) 2021, SocialSweet Inc., all rights reserved. 