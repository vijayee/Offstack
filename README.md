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
The Owner Free File System is the world's first brightnet, instead of anonymizing the network, the data blocks are anonymized and therefore, only meaningless garbage is ever exchanged and stored. This is made possible because of how files are represented in the off system. There is exists two numbers `a` and `b` mathematical relationship such that:
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
as a tuple 
```
{randomChunk, newRandomChunk}
```
A file then can be thought of as a list of tuples of meaningless data. That same data can be considered a representation of an infinitecimal number of files. The meaning of that data is never stored but the representation is returned to the person who stored it in the form of a link that tells the system how to collect and process that random. This link holds the key to the original file and just like a real key grants access rights to the holder indefinitely. Unlike many p2p architectures that use heavy encryption to protect whole files from access the only thing of value to protect is the link. This signifficantly limits the domain and amount of data over which security has to be considered. The method creates both privacy, permanence, replication, and anonymity for no additional overhead. In the case where a node is seized, lost, or hacked there is no data of value available and nothing incriminating can be recovered. Furthermore, the source of the data cannot be determined from its storage. Observation of network activities yield only random data devoid of meaning and purpose. All links can be resolved over http to a web browser or http consuming client, a paradigm native to the web and the backbone of webservices. Additionally, static websites can be served natively from a single link just as a normal webserver would. These properties make The Off system and ideal foundation for decentralized applications.

### The On System
The Owner Free File System Naming System is a darknet that has the goal of extending the functionality of the off system by providing off url storage, content addressing, url shortening, data domains for mutable content. The On System is an entirely seperate network and application from the off System. It acts as a client to the offsystem. Files added through the on system have their content hashed and may be referenced by their hash alone. That hash is then used to determine if that content has been store through the on system before and if so it uses the stored representation of that file. This allows for deduplication of files and conservation of resources on the off system. The protection provided by the properties of the off system would normally be negated by storage of both name and meaning of the data in a cache of links. To preserve these properties on system links are stored in a very particular way. The content hash is used to encrypt the off url and hash of content hash is created to index it on the network. 
```
{<hash of content hash>: <link encrypted with content hash>}
```
The content hash is never actually stored in the system. You cannot access the content without knowledge of the original content hash known only to those who stored the content. Additionally, the on system introduces data domains. This is a method of referencing mutable content such as website or a frequently edited file. Data domains are public keys that link to private key signed records to other off/on system resources or lists of resources. They can only be changed by the holder of the private key. The domains can be referenced by dns services or url resolver plugins to find non static content.

### Vaccuum Tube 
Vaccuum Tube is an anycast Pub/Sub messaging network designed based on Quasar. This provides the ability for applications to communicate with each other regardless of their location or ip. The key mechanism in Quasar is a rendezvousless
event routing infrastructure for performing scalable publish-subscribe to specific groups without requiring per-group state or specific structure in the underlying overlay. In Quasar, peers install a collection of delivery instructions at other nearby peers up to a few hops away. Peerss publish messages to the group by issuing multiple copies of the message to random peers in their routing table. If a message encounters delivery intsructions at a node, it is routed to the member that installed it. A real-world analogy to astronomy is illustrative. Each group member is a black-hole that creates a gravity well around it. Messages are beams of light. Even without knowing the exact location of a black-hole, a beam of light traveling roughly in the direction of the black-hole gets sucked into the gravity well.

### Water Slide
Water slide is a frame work for byzantine fault tolerant raft consensus. Consensus methods are needed in distributed computing for determining an application's state. Raft provides a simple intuitive algorithim that can be easily implemented for all application purposes. Water Slide provide a frame work for constructing raft consensus over any network overlay the application implements.

### Smarteez
Smartees is a frame work for creating smart contract business process management. Much of the focus of smart contracts is being created through Ethereum. Ethereum is a good idea but having autonomously running turing complete code in a trustless environment based on capitalism only invites regular disaster. Developers do not make perfect code all the time and this environment encourages adversarial pursuit of exploiting those vulnerablities for financial gain. This is an architectural problem and a game theory problem more so than a prequesite of smart contracts. Most of what is present is surplus to the requirements of most web applications and business purposes. Instead let us work in trusted environments, though locked down apis so that affects our burdens and blunders are limited. Smarteez does just that. It allows application developers to define api's to the functionality of their application. It then allows you to orchestrate the use of those api's through busines process management workflows and schedulers. This gives our application the ability to maintain itself autonomously while limiting the possible failure paths and vulnerabilities code is subject. Furthermore, no token system is needed to govern the functionality as it will only ever run the methods intended by the developers.    
