##History:

https://paste.fedoraproject.org/533517/83578148/ - initial, JM

https://paste.fedoraproject.org/536623/ - Scoob

https://paste.fedoraproject.org/542498/14859669 - JM

lost :( 

alvinjoelsantos - commit: ee7b7e1

JollyMort - commit: f2a8892

scoobybejesus - commit: 53a5b45

alvinjoelsantos- commit: df603fd

knaccc: https://github.com/alvinjoelsantos/promo-video/issues/3

scoobybejesus: https://github.com/alvinjoelsantos/promo-video/issues/3

scoobybejesus: https://paste.fedoraproject.org/paste/c6UG6HGOXIoZFeo72sZsCF5M1UNdIGYhyRLivL9gydE=

alvinjoelsantos- commit: e14a015, c7e30df, 35062ab, 807d3a0

this one

---

##1) - Intro

Monero is secure, electronic, untraceable cash. It is open-source, decentralized, and freely accessible to all. 
In this video, we will focus on stealth addresses.
 
##2) - Technology recap

Let's take a step back, and recap some concepts from the previous video.
We learned that Monero uses blockchain technology to record transactions.
When Alice owns Monero, it means that she has exclusive control over some outputs.
When Alice sends Monero to Bob, Alice is announcing to the network that she wishes to consume some of her outputs and create a brand new output for Bob.
In other words, a transaction is the transformation of old outputs belonging to one wallet into new outputs belonging to another.
Let's take this a step further, and see how stealth addresses enhance privacy for recipients.

##3) - The Term - Stealth Addresses

The phrase “stealth address” refers to the overall mechanism in Monero, which allows recipients to have a single address that can be publically shared, but still be able to receive payments that can't be linked together or to any specific address.
In our example, Alice would create a random one-time destination for Bob, to which monero are transferred.
Only Alice and Bob are able to verify that this output was made for Bob, and only Bob can consume it in some future transaction.
An outside observer cannot link two addresses together nor tell if any transaction is associated to a public address.
Well, buckle your seatbelts, because we're about to get technical.

##4) - One-time Destinations

A Monero public address consists of two cryptographic keys, a public view key and a public spend key, which are packed together into a 95-character address.
When Alice sends Monero to Bob, Alice’s wallet will unpack Bob's two public keys from his address.
A unique one-time key (aka output) is created with the use of both Bob's public keys and some random data as the ingredients.
It will serve as a container of funds sent to Bob and become part of a transaction which is then broadcast to the blockchain.
The random data is what makes outputs unlinkable because looking at any output it's impossible to tell which 3 ingredients were used to create it.
However, knowing some of them lets you identify it and access to private spend key also to spend it.
The random data and Bob's public view key make a "shared secret".
Even without knowing the random data, Bob can recover the shared secret by using his privete view key.
Adding his public spend key into the mix gives him all 3 ingredients needed to reconstruct the output.
An output's one-time public key can be seen by everyone.
Even though everyone can see the one-time public keys, no one knows which public addresses are associated to any particular transaction.
Bob is able to scan the blockchain and locate outputs that belongs to him by using his wallet’s private view key, and consume those using his private spend key.

##5) - Tie-in to ring signatures

As you can see, the stealth address process protects the privacy of recipients.
The sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of transactions, by including various foreign outputs with the “real” output.
 
##6) - The end?

In our next video, we’ll discuss the ring signature concept in more detail and see how this feature advances untraceability in Monero.
If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
