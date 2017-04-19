## History:
initial, Scoob (Nov. 2016)

ajs - 6091e9a, 39df73f, 2355e1b, beffe23

this one

---

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on ring signatures.
 
## 2) - Technology recap
 
In our last video, we illustrated how stealth addresses in Monero protect a recipient’s privacy by preventing outputs from being associated with their public address.
In every transaction, a one-time destination public key is automatically generated to indicate who can spend an output in a later transaction. 
On the input side of the transaction, the sender's privacy is protected with the use of ring signatures.

## 3) - The Terms - Ring Signatures, Ring CT

A ring signature is a type of digital signature in which a group of possible signers are fused together to produce a distinct signature that authorizes a transaction.
This is analogous to the signing a check from a joint bank account, but with the actual signer remaining anonymous.
The digital signature is made up of the actual signer (the sender) combined with non-signers to form a "ring," where all members are equal and valid.
This feature helps the sender hide the origin of the transaction, becoming in a sense camouflaged from detection among the other ring members.
There is no way an outside observer can tell which of the possible signers belongs to a sender’s wallet.

The non-signers are decoy outputs selected from the blockchain, which are repurposed as "fake" inputs in a new transaction.
Over the course of time, past transaction outputs could be reused in this way multiple times.
A transaction’s “ring size” is the sum of fake inputs plus one (the “real” newly created input, which is destined for a recipient).

To further enhance anonymity, Monero implements a protocol with ring signatures called “Ring Confidential Transactions” (also known as Ring CT).
With Ring CT, the transaction amounts are hidden.

Now at this point, you might ask if the sender and recipient information are private and the amounts are hidden, what would prevent someone from spending the same Monero twice.
This problem is addressed with the use of something called a “key image.”
For every newly created input, a unique key image is generated that can only be spent once.
When a transaction is transmitted to the Monero network, miners will verify that the key image does not already exist in the blockchain in order to prevent double-spends.

Now, let’s walk through an example to see how these concepts tie together.

## 4) – Ring Signatures Transaction

Alice wants to send Monero to Bob with a “mix in” value of four fake inputs.
Alice is able to create these fake inputs by randomly retrieving four past transaction outputs from the blockchain.
Alice’s transaction would have four fake inputs plus the “real” input that is destined for Bob, resulting in a ring size of five.
This forms a group of five possible signers.
An outside observer, including Bob himself, would not know which of the five possible signers belongs to Alice’s wallet.
The amount of Monero being sent to Bob is also unknown by the public.
However, with the key image of the transaction, miners are still able to confirm that the Monero being sent to Bob has not been spent before.
As you can see, Monero protects the privacy of the sender by obscuring the source of outputs and the amounts and in doing so, ensures outputs remain untraceable with plausible deniability.

## 5) - Conclusion

Ultimately, when ring signatures with the Ring CT protocol are used in conjunction with stealth addresses, the privacy of both the sender and recipient are protected in a trustless and verifiably secure manner.

## 6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.