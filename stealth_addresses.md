## History:

https://paste.fedoraproject.org/533517/83578148/ - initial, JM

https://paste.fedoraproject.org/536623/ - Scoob

https://paste.fedoraproject.org/542498/14859669 - JM

lost :( 

alvinjoelsantos - commit: ee7b7e1

JollyMort - commit: f2a8892

scoobybejesus - commit: 53a5b45

alvinjoelsantos- commit: df603fd

knaccc: 3#issue-212874963

scoobybejesus: 3#issuecomment-285545922

scoobybejesus: https://paste.fedoraproject.org/paste/c6UG6HGOXIoZFeo72sZsCF5M1UNdIGYhyRLivL9gydE=

alvinjoelsantos- commit: e14a015, c7e30df, 35062ab, 807d3a0

JollyMort - commit: 3c339f7

alvinjoelsantos - commit: 4de82c2

knaccc: 3#issuecomment-286899474

scoobybejesus: 3#issuecomment-287072833

knaccc: 3#issuecomment-287086144

alvinjoelsantos - commit: 68b2ed0, 004d128, a83eaf0, 7ce43ce

knaccc: 3#issuecomment-287429402

this one

---

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on stealth addresses.
 
## 2) - Technology recap

Let's take a step back, and recap some concepts from the previous video.
We learned that Monero uses a distributed peer-to-peer consensus network to record transaction outputs in a blockchain.
If Alice owns Monero, it means that she has exclusive control over some these outputs.
When Alice sends Monero to Bob, Alice is announcing to the network that she wishes to transfer the value of some of her outputs to a brand new output for Bob, which only he can control.
In other words, a transaction is the transformation of old outputs belonging to one wallet into new outputs belonging to another.
Now let's take this a step further, to see how stealth addresses enhance a user’s privacy.

## 3) - The Term - Stealth Addresses

In every transaction, a stealth address, also known as a one-time public key, is automatically generated and recorded as part of the transaction to indicate who can spend an output in a later transaction.
An outside observer cannot tell if funds are moving from Alice to Bob nor link wallet addressees together by just looking at the blockchain.
Therefore, when Alice sends Monero to Bob, the output Bob receives will not be publicly associated with Bob’s wallet address. 
However, if Alice ever needs to prove that she in fact sent Monero to Bob, her wallet has the ability to verify that payment was sent.
Bob can rest assured that no one else can see when or if any Monero was sent to him.
If Bob were a merchant, this feature would be a great benefit, because no one can tell how many different customers he has, whether any of them are repeat customers, or if he has any customers at all.
Well, buckle your seatbelts, because we are about to go over some fairly technical stuff.

## 4) - One-time Destinations

A Monero wallet address is a 95-character string, which consists of a public view key and a public spend key.
When Alice sends Monero to Bob, Alice’s wallet will use Bob’s public view key and public spend key as well as some random data to generate a unique one-time public key for Bob’s new output. 
Everyone can see the one-time public key on the blockchain, but only Alice and Bob know about the transaction.
The output is created in such a way that Bob is able to locate the output destined for him by scanning the blockchain with his wallet’s private view key.
Once the output is detected and retrieved by Bob’s wallet, he would be able to calculate a one-time private key that corresponds with the one-time public key and spend the relevant output with his wallet’s private spend key.
This whole process occurs without ever having Bob’s wallet address publically linked to any transaction.

## 5) - Tie-in to ring signatures

As you can see, stealth addresses prevent outputs from being associated with wallet addresses.
The sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of outputs.
In our next video, we’ll discuss the ring signature concept in more detail and see how this feature creates untraceability in Monero.

## 6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
