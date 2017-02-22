History:
https://paste.fedoraproject.org/533517/83578148/ - initial, JM
https://paste.fedoraproject.org/536623/ - Scoob
(this one) - JM

1) - Intro
Monero (XMR) is a secure, private, untraceable currency.
Monero seeks to be electronic, private cash.
It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on Monero's stealth addresses.
 
2) - The Term - Stealth Addresses
Every Monero public address is a stealth address!
But how can something public also be stealthy?
We call Monero public addresses "stealth addresses," because they never appear on the blockchain.
The stealth address design takes care of the recipient's privacy because what is received can't ever be tied to an address. //reworded
//nuked :)
But if I give out my public address to receive monero, to where does it actually go? //shortened
Your monero is stored in multiple one-time keys (aka outputs), which only you know are yours. //reworded, let's avoid using address together with one-time destinations or keys? to avoid mixup. keys fits better in the following lines..

3) - Technology recap
Let's take a step back, and recap what we learned in the previous video. 
We learned that Monero transactions are made up of inputs and outputs. //pluralized
When someone sends you monero, he consumes his existing one-time key as input in the transaction and crafts a brand new one for you as an output of the transaction. //simplified, using output as input to create output confused me as well. didn't like how it sounded in the previus vid. either.. but oh well, we learn as we go on.
Further, we mentioned that the sender uses your public address to create an output that only you know belongs to you. //simplified
Let's take this a step further, and get more technical, as to better understand how this works. //simplified

4) - One-time Destinations
Your public address is made up of two parts: a public spend key and a public view key.
When someone sends you monero, their wallet will use each of those public keys to craft a new output. // /s/your/a
Using your public view key, the sender's wallet will compute a random shared secret, only knowable by the sender's wallet and your wallet. //simplified :)
Then the sender's wallet will use the shared secret, along with your public spend key, to create a unique, one-time public key (your output!). //made it tech. accurate
This one-time public key is what resides on the blockchain and can be seen by everyone.
But even though everyone can see it, no one knows who it belongs to, because they can't know the shared secret.
Only your wallet is able to identify the output (one-time public key) as belonging to you, because it can recreate a matching shared secret by using your private view key. //reworded
Every time someone sends monero, a brand new, unique, one-time destination output is created.
The end result is that none of the outputs on the Monero blockchain are linkable to anyone's public address.
 
5) - Tie-in to ring signatures
As you can see, stealth addresses protect the privacy and identity of the recipient of a Monero transaction.
But Monero values the sender's privacy as well.
Using ring signatures, Monero makes it almost impossible to know the source of funds used in a transaction. //reworded
We'll discuss ring signatures and Monero's other privacy features in greater detail in another video.
 
6) - The end?
If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.
