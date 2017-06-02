## History:
initial, Scoob (Apr. 2017)

SamsungGalaxyPlayer - b0eefaa

JM - this one, v2 - implementing kenshi84's comments - ac43af6

SamsungGalaxyPlayer - 0c27e6a

Scoob - this one

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on Ring Confidential Transactions, commonly shortened to RingCT.
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero ring signatures protect senders' privacy by preventing transaction inputs from being distinguishable from one another.
This is accomplished by the digital signature, which can only be proven to be signed by one of the multiple ringmembers.
Additionally, we learned that key images are used to prevent Monero inputs from being spent more than once.
Ring signatures ensure privacy of the sender, since inputs are untraceable.

To increase the privacy of both parties in a transaction, RingCT was implemented to hide transaction amounts.

## 3) - The build-up to Ring CT

Prior to RingCT, Monero required that transaction amounts be split into denominations reflecting one significant digit each.
For example, an output of 12.5 Monero would not be spent as just a single input; rather, it would be broken down into a 10 Monero input, a 2 Monero input, and a 0.5 Monero input.
This technique ensured that there would be ample ring partners for nearly any transaction, since a ring signature could only ring together outputs of the same value.
In this example, there would be three pre-RingCT rings, one for each denomination.

In January 2017, Monero implemented RingCT.
Up until then, third parties examining the blockchain could see the amounts transacted.  
Those third parties generally couldn't ascertain the actual senders of the transactions, due to ring signatures.
And those third parties wouldn't know the recipients of the transactions, due to stealth addresses.
But third parties did have the ability to see how much Monero was being transfered.
This was a source of potential privacy leaks.
RingCT prevents those privacy leaks by forbidding third parties from knowing how much Monero is being transacted.
A month after RingCT was implemented, over 98% of new transactions used RingCT.
After September 2017, the use of RingCT is mandatory for all Monero transactions.

## 4)  RingCT Non-Technical Attributes

All newly created Monero firstly reside in outputs with a visible amount, so everyone can confirm the supply.
Since January 2017, the first time newly-created monero are transfered, those transaction create new RingCT outputs with masked amounts.
As a result of masked amounts, transactions no longer need to be broken down into different denominations.
This means that your wallet is free to pick ring partners from all RingCT outputs, which significantly improves your privacy.
Monero ring signatures do not include both pre-RingCT outputs and masked RingCT outputs in a single ring, so - like newly created Monero - a pre-RingCT output must also be converted to a RingCT output before it can be included in a ring signature with other RingCT outputs.

Let's walk through an example, and then we'll take a deep dive to see how RingCT really works.

## 5) – RingCT Transaction, and Technical Attributes

Imagine you have a RingCT output of 12.56 Monero and would like to send 2.5 Monero to your friend.
Since monero outputs can't be spent twice, you must spend the output in its entirety, and return the change to yourself.
The transaction, then, will have one input of 12.56 Monero and 2 outputs - one of 2.5 monero to your friend, and one of 10.06 monero that is sent back to your wallet as the "change" output.
Even though amounts in RingCT transactions are not revealed, a clever way was devised to ensure the transactions are valid.

To prove that no new monero is created in a transaction, the sum of a transaction's inputs must equal the sum of its outputs.
This was easy to verify pre-RingCT, when amounts were visible; but as we now know, RingCT doesn't allow for this.
Instead, when spending Monero, the inner workings of RingCT require that you cryptographically "commit" to the amount of your outputs.
That is, instead of revealing the values 12.56, 10.06, and 2.5, you cryptographically commit to them.
This "commitment" means you do not publicly reveal the amount you are spending, but you do reveal enough information for the network to confirm the transaction.
A commitment looks like random numbers to a miner; but even though the input and output numbers appear random, they are checked in exactly the same way as a pre-RingCT transaction.
This is called a Pedersen (pronounced pee-der-sen) commitment.
The underlying cryptography of a Pederson commitment guarantees that a check performed on commitments ensures that the amount of monero being sent is the same as the amount of funds available.

The other important part of a RingCT transaction is the "range proof," which guarantees that you don't commit to negative values, with which you could cheat and create new monero.
A range proof cyptographically proves that amounts used in your transaction are greater than 0 and less than some arbitrary number.
Monero uses Borromean signatures to achieve this.
In other words, while no third parties are able to see that you used a 12.56 Monero output to send 2.5 Monero to a friend, those third parties can confirm that you're not spending more than you own, that you're not creating new Monero, and that the transaction is a legitimate one that the network should accept.

[[The following could be reflected on-screen in the commitments section, but should not be narrated.]]

This commitment takes the form of this formula (rct = x*G + a*H(G)).
The two most important variables to consider here are a and x.
H(G) and G are dependent on many other factors that are out outside this video's scope.
a is the actual amount being sent in the transaction, in this case 2.5.
x is a random number acting as a mask, which your wallet software will generate automatically.
In the simplest sense, we can rewrite this equation as rct = a random value + a real value.

You can publish the value 'rct' to the rest of the network as an output, and the network can use this to verify that your transaction is legitimate. This can be used to verify the sum of the inputs used in the transaction equals the sum of the outputs.
However, since an outside observer does not know what the variable x you generated earlier is, he has no way of knowing how much was spent in the transaction.

[[Resume narration below]]

## 5) - Conclusion

As a result of Monero's baked-in privacy features, you are able to transfer Monero to whomever you like; and no one will know how much you sent; no one will know you were the sender; and no one will know to whom you sent it.
These qualities make Monero a leading privacy-centric digital currency, but the innovation doesn't stop here.
In our next video, we'll discuss Kovri, a C++ I2P router designed to provide further transaction obfuscation.

## 6) - The end

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
