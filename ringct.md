## History:
initial, Scoob (Apr. 2017)

SamsungGalaxyPlayer

JM - this one, v2 - implementing kenshi84's comments

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

From Monero's origin until mid-January 2017, Monero amounts had to be automatically split into denominations reflecting one significant digit each.
That is, an amount of 12.5 Monero would never be kept in just one output, but it would be broken down into a 10 Monero output, a 2 Monero output, and a 0.5 Monero output.
This technique ensured that there would be ample ring partners for nearly any transaction, as ring signature could ring together only outputs of the same value.
To further enhance privacy, in mid-January 2017, Monero implemented RingCT.
With Ring CT, transaction amounts are hidden, so splitting into denominations is no longer neccessary.

Up until mid-January 2017, third parties examining the blockchain could see the amounts transacted.  
Those third parties wouldn't know the senders of transactions, due to ring signatures.
And those third parties wouldn't know the recipients of the transactions, due to stealth addresses.
But third parties did have the ability to know how much Monero was being moved.
This led to some potential privacy leaks, as the same value may be transferred through multiple transactions.

Beginning in mid-January 2017, RingCT became the default type of Monero transaction, and only a month later, over 98% of new transactions used RingCT.
RingCT prevents third parties from knowing how much Monero is being transacted.
After September 2017, the use of RingCT will be mandatory for all Monero transactions.

Now, let’s walk through an example to see how these concepts tie together.

## 4) – Ring Signatures Transaction

All the newly created monero firstly reside in outputs with visible amount, so everyone can see the supply.
First time a newly created monero is moved, that transaction creates outputs with masked amounts.
Similarly, any old output must be converted to RCT first after which it can be combined in a ring signature with any other RCT output.
Consequently, transactions no longer have to be broken down into different denominations as before.
This means that your wallet is free to pick ring partners from all RCT outputs, significantly improving privacy.
Let's take a deeper dive to see how a RingCT transaction works.

Imagine you have a RCT input of 12.56 Monero and would like to send 2.5 Monero to your friend.
The transaction will then have one input of 12.56, and 2 outputs: one of 2.5 monero to your friend, and one of 10.06 back to your wallet as change output.
Since monero outputs can't be spent from 2 times, you must always spend it entirely and return the change to yourself.
With this input, you cryptographically commit to some amount without revealing it.
With RCT, instead of revealing the values 12.56, 10.06, and 2.5, you cryptographically commit to them.
The commitment will look like random numbers, but they actually have important features which ensures safety of the mechanism.
To verify that no new money is created, the sum of inputs minus the sum of outputs must be 0.
This is easy to check if you see the numbers.
With commitments, it can be checked exactly the same way!
The only difference is that you're summing some seemingly random numbers, but the sum must again be 0.
The underlying cryptography guarantees that if the sum of commintment is 0, then also the sum of underlying masked values must be 0.
This is called a Pedersen (pronounced pee-der-sen) commitment.
The other important part is a range proof, which guarantees you don't commit to negative values with which you could cheat the sum to 0 and create new money.
It cyptographically proves that amounts used in your transaction are greater than 0 and less than some arbitrary number.
Monero uses Borromean signatures to achieve this.

This commitment takes the form of this formula (rct = x*G + a*H(G)).
The two most important variables to consider here are a and x.
H(G) and G are dependent on many other factors that are out outside this video's scope.
a is the actual amount being sent in the transaction, in this case 2.5.
x is a random number acting as a mask, which your wallet software will generate automatically.
In the simplest sense, we can rewrite this equation as rct = a random value + a real value.

You can publish the value rct to the rest of the network as an output, and the network can use this to verify that your transaction is legitimate. This can be used to verfy the sum of the inputs used in the transaction is the sum of the outputs.
However, since an outside observer does not know what the variable x you generated earlier is, he has no way of knowing how much was spent in the transaction.

## x) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
