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

alvinjoelsantos- commit: e14a015, c7e30df, 35062ab

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

The phrase “stealth address” refers to the overall scheme in Monero, which allows recipients to have a single address that can be publically shared, but still be able to receive payments that are unlinkable to any specific address.
In our example, Alice would create a random one-time destination value on behalf of Bob, where newly created outputs are sent to.
Only Alice and Bob are able to verify where an output was sent with their wallet keys.
An outside observer cannot link two addresses together nor tell if any transaction is associated to a public address.
Well, buckle your seatbelts, because we're about to get technical.

##4) - One-time Destinations

A Monero public address consists of two cryptographic keys, a public view key and a public spend key, which are packed together into a 95-character address.
This results in Monero addresses being nearly twice as long as Bitcoin addresses.
When Alice sends Monero to Bob, Alice’s wallet will unpack Bob's public address to extract his public keys.
A unique output is created with the use of the Bob's public keys and some random data.
Alice’s wallet will encapsulate this new output into a signed container generating a one-time public key, which is then broadcast to the blockchain.
One-time public keys can be seen by everyone. Even though everyone can see the one-time public keys, no one knows which public addresses are associated to any particular transaction.
Bob is able to scan the blockchain and locate outputs that belongs to him by using his wallet’s private view key.

##5) - Tie-in to ring signatures

As you can see, the stealth address process protects the privacy of recipients.
The sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of transactions, by including various foreign outputs with the “real” output.
 
##6) - The end?

In our next video, we’ll discuss the ring signature concept in more detail and see how this feature advances untraceability in Monero.
If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
