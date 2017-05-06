## History:
initial, Scoob (Apr. 2017)

SamsungGalaxyPlayer - this one

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on ring signatures.
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero ring signatures protect senders' privacy by preventing transaction inputs from being distinguishable from one another.
This is accomplished by the digital signature, which can only be proven to be signed by one of the ringmembers.
Additionally, we learned that key images are used to prevent Monero inputs from being spent more than once.
Ring signatures ensure privacy of the sender, since inputs are untraceable.

To increase the privacy of both parties in a transaction, Ring Confidential Transactions were implemented to hide transaction amounts.
Ring Confidential Transactions is commonly referred to as RingCT.

## 3) - The build-up to, and advent of, Ring CT

From Monero's origin until mid-January 2017, Monero ring signatures were constructed by first breaking down the transactions' real input into separate denominations reflecting one significant digit each.  
That is, if the sender owns a single output containing 12.5 Monero, the sender's wallet would first break it into a 10 Monero output, a 2 Monero output, and a 0.5 Monero output. 
This technique ensured that there would be ample ring partners for nearly any transaction.
To further enhance privacy, in mid-January 2017, Monero implemented RingCT.
With Ring CT, transaction amounts are hidden, so denominations containing one significant digit became no longer important.

Up until mid-January 2017, third parties examining the blockchain could see the amounts transacted.  
Those third parties wouldn't know the senders of transactions, due to ring signatures.
And those third parties wouldn't know the recipients of the transactions, due to stealth addresses.
But third parties did have the ability to know how much Monero was transacted between the two parties.
This led to some potential privacy leaks, as the same value may be transferred through multiple transactions.

Beginning in mid-January 2017, RingCT became the default type of Monero transaction, and only a month later, over 98% of new transactions used RingCT.
RingCT prevents third parties from knowing how much Monero is being transacted.
After September 2017, the use of RingCT is mandatory to all Monero transactions.

Now, let’s walk through an example to see how these concepts tie together.

## 4) – Ring Signatures Transaction

Instead of using an entire input in a transaction, RingCT uses a fraction of each input that only the sender knows.
Consequently, transactions were no longer broken down into different denominations as before.
Let's take a deeper dive to see how a RingCT transaction works.

Start with the one input you do control and want to send in a transaction. Imagine you have an input of 12.56 Monero and would like to send 2.5 Monero to your friend.
With this input, you cryptographically commit to pay a certain value. To simplify this explanation, suppose you commit to pay the 2.5 Monero from your 12.56 Monero input, though the amount commited can be greater if you send an output back to yourself. This is called a Pedersen (pronounced pee-der-sen) Commitment.

This commitment takes the form of this formula (rct = x*G + a*H(G)).
The two most important variables to consider here are a and x.
H(G) and G are dependent on many other factors that are out outside this video's scope.
a is the actual amount being sent in the transaction, in this case 2.5.
x is a random number acting as a mask, which your wallet software will generate automatically.
In the simplest sense, we can rewrite this equation as rct = a random value + a real value.

You can publish the value rct to the rest of the network as an output, and the network can use this to verify that your transaction is legitimate. This can be used to verfy the sum of the inputs used in the transaction is the sum of the outputs.
However, since an outside observer does not know what the variable x you generated earlier is, an outside observer has no way of knowing how much was spent in the transaction.

## x) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
