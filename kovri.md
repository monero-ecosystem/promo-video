Kovri Lightweight C++ I2P Router Script

Version 1 - sgp
Version 2 - scoobs

Until this point, this video series has covered how Monero obfuscates information stored on the blockchain. 
Ring signatures obscure the sender.
Stealth addressing prevents anyone but the sender and the recipient from knowing the recipient owns Monero.
RingCT hides the amount of Monero transmitted.
However, some personally identifiable information can still be leaked in the process of sending Monero.
This video will focus on a technology that closes that gap, called Kovri.

Suppose Alice wants to send a transaction to Bob. 
She generates a transaction on her local device, and gets ready to broadcast it to the network, so it can be included in the next block.
Alice is connected to only a small portion of the nodes on the Monero network. 
Her transaction request will need to reach as many nodes as possible - ideally all of them - for her to have the greatest chance of this transaction getting included in the next block. 
Let's say she is connected to five other nodes, so she broadcasts her transaction to all five. 
These five nodes then forward her transaction to all the nodes they are connected to, and so on, until many (or all) nodes have this transaction.

Unfortunately, Alice is taking a risk to broadcast her transaction. 
Some nodes on the network may be logging the IP address for all new transactions. 
An IP address is like your home address for your internet connection. 
An attacker does not know whether the first IP they receive the transaction from is the real sender.
Nor do they know any transaction information, such as the sender, amount, or recipient. 
However, the attacker could make an educated guess to associate a specific transaction, such as the one Alice created in this example, with an IP address.

An attacker with enough resources could then knock on Alice's door and demand that Alice hand over her private keys so that they can find out more information. 
Alternatively, they could purposefully attempt to block her transaction from being broadcast to the rest of the network. 
This sort of attack is called a Sybil attack.

What can be done to mitigate this? 

Alice does not know which nodes log her IP address, so she can't simply avoid the malicious nodes. 
Her only choice is to hide her IP address.
There are several ways to hide your IP address, including with Tor, a trusted VPN, or I2P. 
We will focus on I2P in today's video, since this is the network on which Kovri operates.

In a sentence, Kovri is a lightweight router written in C++, compatible with cryptocurrencies, and built for the I2P network. 
I2P stands for Invisible Internet Protocol.
I2P is a layer of the internet that allows for all connections in the network to be private. 
In contrast with regular internet routing or TOR's onion routing, I2P utilizes what it refers to as garlic routing.
Instead of connecting with participants directly or through TOR nodes, such as going directly to a website, all information is encrypted and relayed through other I2P routers in the network. 

Since I2P routers know little or no information about the data they are sending, where it originated, or its destination, all information in this network is private and anonymous.
Nodes that log Monero traffic will now get a meaningless .i2p address, which has no connection to a node's real IP address.
Thus, even if nodes continue to log information, they will not learn anything from passive surveillance.
Now, when Alice sends her transaction through I2P with the Kovri router, an attacker is no longer able to associate her IP address with her transaction. 

Furthermore, suppose Alice has an internet service provider that does not want her to use Monero. 
Alice can optionally send all the Monero sync data, not just the transaction broadcast, through I2P. 
Now, her ISP will not know that she is using Monero, improving Monero's censorship resistance.

Kovri will come bundled with future Monero releases, and it will be enabled by default to broadcast the transaction through the I2P network.

In summary, Kovri is a software router that allows Monero users to connect to the private I2P network to send transactions anonymously. 
Malicious nodes are no longer able to threaten users who create these transactions or block them from propagating across the network.

To learn monero about Kovri, go to getkovri.org. To learn more about Monero, go to getmonero.org.
