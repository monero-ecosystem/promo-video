##History:

https://paste.fedoraproject.org/533517/83578148/ - initial, JM

https://paste.fedoraproject.org/536623/ - Scoob

https://paste.fedoraproject.org/542498/14859669 - JM

lost :( 

https://github.com/alvinjoelsantos/promo-video/blob/master/stealth_addresses.md - ajs

---

##1) - Intro

Monero is a secure, private, untraceable currency.
Monero seeks to be electronic, private cash.
It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on Monero's stealth addresses.
 
##2) - Technology recap

Let's take a step back, and recap what we learned in the previous video.
We learned that Monero transactions are made up of inputs and outputs.
When someone sends you Monero, they deplete an existing output to form a brand new output of the transaction.
Furthermore, we mentioned that the sender uses your public address to create an output that only you know belongs to your wallet.
Let's take this a step further, and get more technical to gain a better understand of how this works.


##3) - The Term - Stealth Addresses

Every Monero public address is a stealth address!
But how can something public also be stealthy?
We call Monero public addresses "stealth addresses", because they never appear on the blockchain.
The stealth address is designed to protect the recipient's privacy given that what is received can't ever be tied to a specific public address.
But if I give out a public address to receive Monero, where does it actually go you might ask?
Well, your Monero is stored in multiple one-time public keys (also known as outputs), which are controlled by your wallet.

##4) - One-time Destinations

Your public address is made up of two parts: a public spend key and a public view key.
When someone sends you Monero, their wallet will use each of those keys to form a new output.
Using your public view key, the sender's wallet will compute a random shared secret, which will be recognized only by your wallet.
Then, the sender's wallet will use the shared secret, along with your public spend key, to create a unique, one-time public key (your output!).
This one-time public key is what resides on the blockchain and can be seen by everyone.
Even though everyone can see the output, no one knows which outputs are associated to any particular public address, because an outside observer would not know the shared secret.
Only your wallet is able to identify the output (one-time public key) as belonging to you, because it can compute the shared secret by using your private view key.
 
##5) - Tie-in to ring signatures

As you can see, stealth addresses protect the privacy and identity of recipients.
On the input side of the transaction, the sender's privacy is covered with the use of ring signatures.
Ring signatures help obfuscate the source of transactions by using a number of foreign outputs pulled from the blockchain combined with the “real” output, to authorize the sending of Monero to a recipient.
We'll discuss ring signatures and Monero's other privacy features in greater detail in another video.
 
##6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
