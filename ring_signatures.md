## History:
initial, Scoob (Nov. 2016)

ajs - 6091e9a, 39df73f

this one

---

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on ring signatures.
 
## 2) - Technology recap
 
In our last video, we illustrated how stealth addresses in Monero protect a recipient’s privacy by preventing outputs from being associated with their public address.
In every transaction, a one-time destination public key is automatically generated to indicate who can spend an output in a later transaction. 
On the input side of the transaction, the sender's privacy is protected with the use of ring signatures.

## 3) - The Term - Ring Signatures

A ring signature is a type of digital signature in which a group of possible signers are combined to produce a distinct signature that authorizes a transaction.
This is analogous to the signing of a check from your bank.
However, the actual signer is anonymous, because a ring includes the signatures of the sender hidden among other members that are non-signers.
The non-signers are old transaction outputs selected from the blockchain, which are repurposed as decoy inputs in a new transaction.
Over the course of time, old transaction outputs could be reused in this way multiple times.
A transaction’s “ring size” is the sum of these outputs plus one (the “real” newly created output, which is destined for a recipient).
In a ring where you have the actual signer and non-signers, all members are equal and valid. 
There is no way an outside observer can tell which of the possible signers belongs to a sender’s wallet. 
This feature helps the sender hide the origin of the transaction, becoming in a sense camouflaged from detection.
Now, let’s walk through an example to see how ring signatures work.

## 4) – Ring Signatures Transaction

Alice wants to send Monero to Bob with a “mix in” value of 4 transaction outputs.
Alice is able to pull the outputs by connecting to an active node or pulling the outputs offline from a locally saved copy of the blockchain.
In our example, Alice’s transaction would have a ring size total of five, which forms a group of five possible signers.
An outside observer, including Bob himself, would not know which of the five possible signers actually belongs to Alice’s wallet.
As you can see, ring signatures in Monero protects the privacy of the sender by obscuring the source of outputs and in doing so, ensures outputs remain untraceable with plausible deniability.
Ring signatures also helps maintain Monero’s fungibility in that one Monero is identical to any other Monero no matter the source of the transaction.

## 5) - Tie-in to RingCT

Ultimately, when ring signatures are used in conjunction with stealth addresses the privacy of both the sender and recipient are protected.
In addition, Confidential Transactions (also known as RingCT) enhances privacy by hiding the amount of Monero being sent to a recipient. 

## 6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.