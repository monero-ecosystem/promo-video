## History:
initial, Scoob (Apr. 2017)

SamsungGalaxyPlayer - b0eefaa

JM - implementing kenshi84's comments - ac43af6

SamsungGalaxyPlayer - 0c27e6a

Scoob - f8f54ad

ajs - 018f931

JM - c6cf2b8

anonimal - this one - minor fixes

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on Ring Confidential Transactions, commonly known as RingCT.
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero ring signatures protect senders' privacy by preventing transaction inputs from being distinguishable from one another.
This is accomplished by the use of digital signatures, where there is an actual signer hidden among multiple ring members to authorize a transaction.
Additionally, we learned that key images are used to prevent Monero inputs from being spent more than once.
Ring signatures ensure privacy of the sender, since inputs are untraceable.
To increase the privacy of both parties in a transaction, RingCT was implemented to hide transaction amounts.

## 3) - The build-up to Ring CT

Prior to the implementation of RingCT, Monero required transaction amounts to be split into specific denominations.
For example, an output of 12.5 Monero would be broken up into three separate rings in the amounts of 10, 2, and 0.5.
This technique ensured that there would be ample ring members, since a ring signature could only ring together outputs of the same value.
However, a downside to this process is that an outside observer was able to see the amounts transacted.
To address this shortcoming, Monero activated RingCT in January 2017.
RingCT prevents privacy leaks by hiding transaction amounts in the blockchain.
A month after RingCT was activated, approximately 98% of new transactions were using the RingCT protocol.
After September 2017, the use of RingCT will be mandatory for all Monero transactions.

## 4)  RingCT Non-Technical Attributes

Today with RingCT, newly created Monero firstly resides in outputs that have visible amounts.
When new Monero is transferred for the first time, RingCT outputs with masked amounts are generated.
As a result, transactions no longer need to be broken down into different denominations.
This means that a wallet is free to pick ring members from any RingCT outputs, which significantly improves privacy.
It should be noted that Monero ring signatures can't include both pre-RingCT outputs and masked RingCT outputs in a single ring, so - like newly created Monero - a pre-RingCT output must first be converted to a RingCT output before it can be included in a ring signature with other RingCT outputs.
Let's walk through an example, and then take a deep dive to see how RingCT works.

## 5) – RingCT Transaction, and Technical Attributes

Alice has an output of 12.56 and would like to send Bob 2.5 Monero.
Since outputs can't be spent twice, Alice needs to spend the output in its entirety and return the change to herself.
So, Alice's transaction would have one input of 12.56 Monero and 2 outputs - one that is 2.5 Monero designated for Bob and another that is 10.06 Monero, which is sent back to her wallet as "change" of the transaction.
To prove that Monero has not been fraudulently fabricated in a transaction, the sum of a transaction's inputs must equal the sum of its outputs.
Due to cryptographic properties of RingCT, Alice is required to "commit" to the amount of an output, revealing just enough information for the network to confirm the transaction, while not publicly disclosing the amount she is spending.
Although commitments look like random numbers, miners are still able to confirm that the amount of Monero being sent to Bob is the same as the amount of funds available. [See Note 1]
Another important aspect of a RingCT transaction is the "range proof", which prevents senders from committing to negative values in order to secure the supply of Monero.
A range proof cyptographically proves the amounts used in a transaction is greater than 0 and less than some arbitrary number.
While an outside observer is unable to see the actual amounts in outputs of a transaction, they are able to confirm that the transaction is a legitimate one that the network should accept.

## 6) - Conclusion

As a result of Monero's baked-in privacy features, users are able to transfer Monero to whomever they like; and no one would know how much was sent nor who the sender or recipient were.
These qualities make Monero a leading privacy-centric digital currency, but the innovation doesn't stop there.
In our next video, we'll discuss Kovri: an anonymizing router that will make Monero transactions more secure than ever before.

## 7) - The end

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.

--------------------------------------------------

Note 1. The following could be reflected on-screen in the commitments section, but should not be narrated.

This commitment takes the form of this formula (rct = x*G + a*H(G)).
The two most important variables to consider here are a and x.
H(G) and G are dependent on many other factors that are out outside this video's scope.
a is the actual amount being sent in the transaction, in this case 2.5.
x is a random number acting as a mask, which your wallet software will generate automatically.
In the simplest sense, we can rewrite this equation as rct = a random value + a real value.

You can publish the value 'rct' to the rest of the network as an output, and the network can use this to verify that your transaction is legitimate. This can be used to verify the sum of the inputs used in the transaction equals the sum of the outputs.
However, since an outside observer does not know what the variable x you generated earlier is, he has no way of knowing how much was spent in the transaction.
