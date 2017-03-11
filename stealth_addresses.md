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

JollyMort - commit: 3c339f7

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
In our example, Alice would create a random one-time destination for Bob, to which Monero are transferred.
Only Alice and Bob are able to verify that this output was made for Bob, and only Bob can consume it in some future transaction.
An outside observer cannot link two addresses together nor tell if any transaction is associated to a public address.
Well, buckle your seatbelts, because we're about to get technical.

##4) - One-time Destinations

A Monero public address consists of two cryptographic keys, a public view key and a public spend key, which are packed together into a 95-character address.
When Alice sends Monero to Bob, Alice’s wallet will unpack Bob's public keys from his address.
Alice’s wallet will then create a unique one-time key (also known as an output), which is made up of 3 components: Bob's public view key and public spend key as well as some random data.
The one-time key will serve as a container of the Monero sent to Bob, which is broadcast to the blockchain as a transaction.
Everyone can see an output’s one-time key, but no one knows which public addresses are connected to any particular transaction.
When an outside observer looks at the blockchain, it's impossible to tell which of the 3 components were used to create Bob's output.
However, knowing some of the components allows a person to identify an output and if the person has access to a private spend key associated with the output, they would be able to spend it.
So, the random data and Bob's public view key can be considered as a "shared secret."
Even without knowing the random data, Bob can still recover the shared secret by using his wallet's private view key and public spend key to reconstruct the output sent by Alice.
To receive Monero in to his wallet, Bob is now able to scan the blockchain and locate outputs that belongs to him by using his private view key and consume those outputs by using his private spend key.
This process occurs without ever having Bob’s public address linked to any transaction.

##5) - Tie-in to ring signatures

As you can see, the stealth address process protects the privacy of recipients.
The sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of transactions, by including various foreign outputs with the “real” output.
 
##6) - The end?

In our next video, we’ll discuss the ring signature concept in more detail and see how this feature advances untraceability in Monero.
If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
