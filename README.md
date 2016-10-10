# Offstack
A Decentralized Application (DAPP) Framework based on the Off System
## Overview
The Offstack consists of a network of networks and design frameworks for building decentralized web applications. The tool consist of :
* The Off System
* The On System
* Water Slide
* Vaccuum Tube
* Smarteez

##Rationale
There is a race on to decentralize all the things. Much of the toolsets, languages and design patterns are alienating to the average web or fullstack developers. Furthermore most of the popular distributed computing tools that operate in peer2peer are mercantile and trustless (ie: Bitcoin, Ethereum, MaidSafe). Because they use tokens to monetize the network resources it uses as incentives for their user, it also incentivizes adversarial behavior both from and economic standpoint and a network security standpoint. This is not a needed or desireable property for many purposes of the applications and websites on the internet. So when trying to create a foundation for a decentralized internet using these tools as a basis for non-competitive or non-commercial uses ties their ability to operate and maintain themselves to the threats and security problems of finanacial networks. Introducing more likely points of failure for infrastructures not purely financial or capitalistic in nature.

Only since Bitcoin has p2p and decentralization become synonymous with tokens. Prior to it was mostly associated with p2p file sharing, content distribution, and distributed computing. As a result this has drawn much need attention and poplarity to this field of computer science. However, the purpose for this is because it appeals to the "get rich quick" mentality of commodities traders. This is a very capatilistic and subsequently limited perspective on the value of this technology. This actually ties the failings of our current captilistic systems to the creativity surrounding the use of these tools and technologies. These ideas can most certainly overcome those failings and many other universal human needs if we approach their use with a slightly different perspective. We should be trying to provide access to as much of a resource as is needed so long as it does not infringe upon the quality of user experience for other particpants in a network. Trying to tokenize a resource makes strong statements on the nature of its value while simultaneously stifling its value by creating a barrier to its use. 

In trustless environments this is needed to guarantee and incentivize performance of duties. In trusted environments this is not needed or desireable. For many applications and websites the access to their functionality is enough to incentivize the participation in the network and its maintenance. This can be seen in the bittorent network. It has been shown through the Folding@Home project that for altruistic purposes people are willing to donate their unsused computing resources to causes that benefit all of humanity. So it stands to reason that for mutual benefit of access alone people can compute the functionality of and store the data of a p2p application cooperatively. Offstack is attempting to solve this problem, for every computing area that the this rationale and technology applies, in a manner that does not alienate the skillset of the average web developers and their best practices.

## Key Architecture Points
Offstack is designed to encourage human contribution by making it trivial to do so. The only incentive for participation is access to network resources. It then returns access to those resources back to the participants at no additional cost. With a model like this great emphasis has to be placed on privacy of the participants and respect for their resources. This is accomplished through ingenious architecture rather than brute force restrictions. This section will detail how each layer accomplishes this.

### The Off System
This is the world's first brightnet, instead of anonymizing the network, the data blocks are anonymized and therefore, only meaningless garbage is ever exchanged and stored. This is made possible because of how files are represented in the off system. There is exists two numbers `a` and `b` mathematical relationship such that:
```
a ⊕ b = C 
```
This creates a third number `c` that has a parity relationship with `a` and `b` such that
```
a ⊕ c = b 
```
and 
```
b ⊕ c = a 
```
meaning that a representation of each indvidual number can be created from any of the other two numbers. Computer data is just arbitrarily large numbers with the same properties as above. When storing to the Off System, a peer breaks down a file into chunks and creates a representation of it from random junk data contributed from other peers and theirself such that:
```
chunkOfFile ⊕ randomChunk = newRandomChunk
```
The OffSystem will never store the original data it will store the representation
```
randomChunk ⊕ newRandomChunk
```
but instead stores a tuple 
```
{randomChunk, newRandomChunk}
```
A file then can be thought of as a list of tuples of meaningless data. That same data can be considered a representation of an infinitecimal number of files. The meaning of that data is never stored but the representation is returned to the person who stored it in the form of a link that tells the system how to collect and process that random. This link holds the key to the original file and just like a real key grants access rights to the holder indefinitely. Unlike many p2p architectures that use heavy encryption to protect whole files from access the only think of value to protect is the link. 


