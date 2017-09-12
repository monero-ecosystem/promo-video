Kovri Lightweight C++ I2P Router Script

Until this point, this video series has covered how Monero obfuscates information stored on the blockchain.
Ring signatures obscure the sender.
Stealth addressing prevents anyone but the sender and the recipient from knowing the recipient owns Monero.
RingCT hides the amount of Monero transmitted.
However, some personally identifiable information can still be leaked in the process of sending Monero.
This video will focus on a technology that closes that gap, called Kovri.

Suppose Alice wants to send a transaction to Bob.
She generates a transaction on her local device, and gets ready to broadcast it to the network, so it can be included in the next block.
Alice is connected to only a small portion of the nodes on the Monero network. Her transaction request will need to reach as many nodes as possible - ideally all of them - for her to have the greatest chance of this transaction getting included in the next block.
Let's say she is connected to five other nodes, so she broadcasts her transaction to all five.
These five nodes then forward her transaction to all the nodes they are connected to, and so on, until many (or all) nodes have this transaction.

Unfortunately, Alice takes a risk to broadcast her transaction.
Some of the nodes on the network may be logging the IP addresses that they get transaction requests from.
An IP address is like your home address for your internet connection.
Attackers will try to associate transactions with the IP addresses they originate from.
They do not know anything about what address a transaction is coming from, where it is going to, or what the amount is.

However, an attacker with enough resources could knock on Alice's door and demand that she tell them this information. 
Alternatively, they could purposefully attempt to block her transaction from being broadcast to the rest of the network.

So what can Alice do to mitigate these threats?

Alice does not know which nodes log her IP address, so she can't simply avoid the malicious nodes.
Her only choice is to hide her IP address.
There are several ways to hide an IP address, including with Tor, a trusted VPN, or I2P.
We will focus on I2P in today's video, since this is the network on which Kovri operates.

In a sentence, Kovri is a lightweight router compatible with cryptocurrencies and built for the I2P network.
I2P stands for Invisible Internet Protocol.
I2P is a layer of the internet that allows for all connections in the network to be private.
In contrast with regular internet routing or TOR's onion routing, I2P utilizes what it refers to as garlic routing.
Instead of connecting with participants directly or through TOR nodes, such as going directly to a website, all information is encrypted and relayed through other I2P routers in the network.

Since I2P routers know little or no information about the data they are sending, where it originated, or its destination, all information in this network is private and anonymous.
If Alice sends her transaction with Kovri, nodes that log Monero traffic will no longer get her real IP address, rendering these passive surveillance tactics useless.

Now let’s imagine a different scenario.
Suppose Alice has an internet service provider that does not want her to use Monero, who send her a warning saying so.
Alice can optionally send all the Monero sync data, not just the transaction broadcast, through I2P.
Now, her Monero connections are hidden from her ISP.
This improves Monero's censorship resistance, since other people no longer know who is running a Monero node and demand that they be shut down.

Let’s look at one last scenario.
Suppose George is the operator of a mining pool that controversially donates a portion of the block reward to a political party.
Other nodes could purposefully reject his solved blocks to express their disagreement with this policy.
This sort of attack is called a Sybil attack.
However, if George can send his solved blocks through Kovri, then no one can censor the work from his pool, since they no longer know that his pool created it.

Kovri will come bundled with future Monero releases, and it will be enabled by default to broadcast the transaction through the I2P network.
It will feature a common API that can be used by any cryptocurrency, not just Monero.

In summary, Kovri is a software router that allows Monero users to connect to the private I2P network to send transactions anonymously.
Malicious nodes can no longer threaten users who create these transactions or block them from propagating across the network. 
Kovri will revolutionize peer-to-peer connections and increase network resiliency and privacy worldwide.

To learn more about Kovri, go to getkovri.org. To learn more about Monero, the cryptocurrency behind this project, go to getmonero.org.
