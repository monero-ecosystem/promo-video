## History:
initial, Scoob (Nov. 2016)

ajs - 6091e9a, 39df73f, 2355e1b, beffe23, a18d8de

JM - a18d8de

Scoob - 43af275

SamsungGalaxyPlayer - 4a4e99f

ajs - this one

---

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on ring signatures.
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero stealth addresses prevent outputs from being associated with a recipient's  public address.
This is accomplished by the use of one-time destination public keys.
One-time public keys are only spendable by the recipient, and only the recipient is able to detect their designated output on the blockchain.
Since all outputs are unlinkable, the privacy of the recipient is ensured.

On the input side of the transaction, the sender's privacy is protected with the use of ring signatures.

## 3) - The Term - Ring Signatures, Key Image

A ring signature is a type of digital signature in which a group of possible transaction signers are fused together to produce a distinctive signature that authorizes a transaction.
This can be thought of as analogous to the signing of a check from a joint bank account, but with the actual signer remaining unknown.
The digital signature is made up of the actual signer combined with non-signers to form a "ring," where all members are equal and valid.
A signer is the one-time spend key that corresponds with the output being spent from the sender's wallet.
The non-signers are past transaction outputs pulled from the blockchain, which act as decoys.
The real output and the decoy outputs together make up the inputs of the transaction.
To a third party, all of the inputs appear equally likely to be the real input being spent in the transaction.
This feature helps the sender hide the origin of the transaction, by making themself indistinguishable from the other ring members.


You may now be asking yourself, "if there is no way for a third party to verify which intput is being spent, what would prevent someone from spending the same output twice?"
This potential issue is addressed by the use of “key images.”
A key image is a cryptographic key derived from the real output. 
There can exist only one key image for each output on the blockchain.
A list of all used key images is maintained in the Monero blockchain, enabling miners to ensure that no Monero are spent twice.
It is not possible to determine which output created which key image.
Let's go through an example.

## 4) – Ring Signatures Transaction

Alice wants to send Monero to Bob with a “ringsize” value of five inputs. 
One of the five inputs will be the real input Alice is spending.
Alice's wallet will pick the remaining four decoy inputs by randomly retrieving past transaction outputs from the blockchain.
This forms a group of five inputs with five possible signers, but only one input is actually getting spent.

As usual, a brand new output destined for Bob is created.
To an outside observer, including to Bob himself, it's not clear which input was truly spent from Alice’s wallet.
However, with the key image, the network is able to verify that the Monero being sent to Bob has not been spent before.

As you can see, using ring signatures Monero protects the privacy of the sender by obscuring the source of inputs, and in doing so, ensures that outputs remain untraceable.

To increase the privacy of both parties in a transaction, Ring Confidential Transactions were implemented to hide transaction amounts.
Ring Confidential Transactions is commonly referred to as RingCT and brings an improvement to the ring signatures discussed in this video.
We'll talk about Ring CT in our next video.

## 6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
