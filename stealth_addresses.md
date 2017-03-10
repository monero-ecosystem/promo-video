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

this one

---

##1) - Intro

Monero is secure, electronic, untraceable cash. It is open-source, decentralized, and freely accessible to all. 
In this video, we will focus on stealth addresses.
 
##2) - Technology recap

Let's take a step back, and recap some concepts from the previous video.
We learned that Monero exist on the blockchain in the form of outputs.
When you own Monero, it means that you have exclusive control over some of these outputs.
When you transmit funds to a recipient, you are announcing to the network that you wish to deplete some of your outputs to create brand new outputs for someone else.
The sender uses the recipient’s public address to create a unique output in such a way that only the intended recipient is able to recognize and spend the output.
As a result, outputs are unlinkable to, or associated with, any public address. Well, buckle your seatbelts, because we're about to get technical.

##3) - The Term - Stealth Addresses

Stealth Addresses could be seen in two ways. 
In one sense, every public address is a stealth address given that public addresses never appear on the blockchain.
In another sense, the unique output that is created for a transaction could also be referred to as a stealth address seeing that it is the destination where funds are transmitted to, but not associated with the recipient’s public address.
Stealth addresses are what protect the privacy of Monero recipients.

##4) - One-time Destinations

The recipient's public address consists of two cryptographic keys, a public view key and a public spend key.
When someone sends Monero, the sender’s wallet will use these keys to compute a random shared secret only knowable by the sender's wallet and recipient's wallet; the sender’s wallet will then create a unique, one-time public key (your output!) to encapsulate the transaction with the shared secret.
You heard right; Monero outputs are also called one-time public keys. One-time public keys are what reside on the blockchain and can be seen by everyone.
Even though everyone can see the one-time public keys, no one knows which public addresses are associated to any particular transaction, because outside observers do not know the shared secret.
Recipients are able to recompute the shared secret with their wallet’s private view key and identify outputs (one-time public keys) that belong to them.
 
##5) - Tie-in to ring signatures

As you can see, stealth addresses protect the privacy of recipients.
On the other side of the transaction, the sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of transactions, by including various foreign outputs with the “real” output.
 
##6) - The end?

In our next video, we’ll discuss the ring signature concept in more detail and see how this feature advances untraceability in Monero.
If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
