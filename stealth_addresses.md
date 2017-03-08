##History:

https://paste.fedoraproject.org/533517/83578148/ - initial, JM

https://paste.fedoraproject.org/536623/ - Scoob

https://paste.fedoraproject.org/542498/14859669 - JM

lost :( 

alvinjoelsantos - commit: ee7b7e1

JollyMort - commit: f2a8892

scoobybejesus - commit: 53a5b45

---

##1) - Intro

Monero is a secure, private, untraceable currency.
Monero seeks to be electronic, private cash.
It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on Monero's stealth addresses.
 
##2) - Technology recap

Let's take a step back, and recap some concepts from the previous video.
We learned that Monero transactions are made up of inputs and outputs.
When someone sends you Monero, the transaction they create depletes an existing output of theirs to form a brand new output for you.
Furthermore, we mentioned that the sender uses your public address to create an output that only your wallet knows belongs to you.
Let's take this a step further, to gain a better understand of how this works.

##3) - The Term - Stealth Addresses

Every Monero public address is a stealth address!
But how can something public also be stealthy?
We call Monero public addresses "stealth addresses," because they never appear on the blockchain.
Since Monero's blockchain does not store balances in public addresses, we see that stealth addresses protect the recipient's privacy.
Now you might ask, "if I give out my public address to receive monero, where is the monero actually sent?"
This is where things get a little technical.
Your monero is stored in multiple one-time public keys (a more precise term for Monero's outputs), which are controlled by your wallet.
Let's go even more in-depth to see how this works.

##4) - One-time Destinations

Your public address is made up of two parts: a public spend key and a public view key.
When someone sends you Monero, their wallet will use each of those keys to form a new output.
Using your public view key, the sender's wallet will compute a random shared secret, only knowable by the sender's wallet and your wallet.
Then the sender's wallet will use the shared secret, along with your public spend key, to create a unique, one-time public key (your output!).
This one-time public key is what resides on the blockchain and can be seen by everyone.
Even though everyone can see the output, no one knows which public address it was sent to, because outside observers can not know the shared secret.
Using your private view key, your wallet can recompute the shared secret; therefore, only your wallet is able to identify the output (one-time public key) as belonging to you.
 
##5) - Tie-in to ring signatures

As you can see, stealth addresses protect the privacy and identity of recipients.
On the input side of the transaction, the sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of transactions, by including various foreign outputs with the “real” output.
We'll discuss ring signatures and Monero's other privacy features in greater detail in another video.
 
##6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
