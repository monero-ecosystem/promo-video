## History:
initial, Scoob (Apr. 2017)

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on ring signatures.
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero ring signatures protect senders' privacy by preventing transaction inputs from being distinguishable from one another.
This is accomplished by the digital signature, which can only be proven to be signed by one of the ringmembers.
Additionally, we learned that key images are used to prevent Monero inputs from being spent more than once.
Ring signatures ensure privacy of the sender, since inputs are untraceable.

To increase the privacy of both parties to a transaction, Ring Confidential Transactions were implemented to hide transaction amounts.
Ring Confidential Transactions is commonly referred to as RingCT.

## 3) - The build-up to, and advent of, Ring CT

From Monero's origin until mid-January 2017, Monero ring signatures were constructed by first breaking down the transactions' real input into separate denominations reflecting one significant digit each.  
That is, if the sender owns a single output containing 12.5 Monero, the sender's wallet would first break it into a 10 Monero output, a 2 Monero output, and a 0.5 Monero output. 
This technique ensured that there would be ample ring partners for nearly any transaction.
To further enhance privacy, in Mid-January 2017, Monero implemented “Ring Confidential Transactions” (also known as Ring CT).
With Ring CT, transaction amounts are hidden, so denominations containing one significant digit became no longer important.

Up until mid-January 2017, third parties examining the blockchain could see the amounts transacted.  
Those third parties wouldn't know the senders of transactions, due to ring signatures.
And those third parties wouldn't know the recipients of the transactions, due to stealth addresses.
But third parties did have the ability to know how much Monero was transacted between the two parties.

Beginning in mid-January 2017, RingCT became the default type of Monero transaction.
RingCT prevents third parties from knowing how much Monero is being transacted.
After September 2017, the use of RingCT is mandatory to all Monero transactions.

Now, let’s walk through an example to see how these concepts tie together.

## 4) – Ring Signatures Transaction

