## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all. In this video, we will focus on an anonymity technology, called Kovri.

## 2) - Technology recap

Up to now, we have covered how Monero obfuscates information stored on the blockchain.
Ring signatures obscure the sender.
Stealth addresses prevent outside observers from knowing the receiving address.
And RingCT hides the amount of Monero that's transmitted.
However, some personally identifiable information may be leaked at the network level when making a transaction.
This privacy leak is addressed with Kovri.

## 3) - The Term - Kovri

Kovri is a free, decentralized, anonymity technology based on I2P's open specifications.
Kovri uses both encryption and sophisticated routing techniques to create a private overlay-network across the Internet.
This protected overlay allows users to hide their geographical location and IP address.
An IP address is like a home address for the Internet, so this is quite sensitive information, to say the least.
Let's go through a few scenarios to see how this lightweight, security-focused software helps strengthen the unique privacy properties of Monero.

## 4) Examples

Suppose Alice wants to send a transaction to Bob, and she begins the transaction.
In order for her transaction to have the greatest chance of being included in the next block, she needs to reach as many nodes as possible.
Alice connects to five nodes and these nodes then forward the transaction to other nodes, which in turn rebroadcast it repeatedly until many (or all) nodes in the network have this transaction.
Unfortunately, Alice takes a risk when broadcasting her transaction.
Some nodes may be logging IP addresses when transaction requests are received.
Even though wallet addresses and the amount of Monero remain private, an attacker with enough resources could attempt to associate transactions with IP addresses to determine where transactions originate from.
This could potentially lead to an attacker knocking on Alice's door or blocking her transaction from the rest of the network.

Now let’s imagine a different scenario.
Suppose Charlie wants to support the Monero network by running a full node at his home.
After a few weeks, he receives a cease and desist letter from his Internet Service Provider informing him that running a node is a violation of the terms of service.

Or consider this, suppose Dave is an operator of a mining pool that donates a portion of block rewards to a political party or controversial cause.
Other nodes could purposefully reject his solved blocks to express their disagreement with his political or social views.

Alice, Bob, Charlie, and Dave all have at least one thing in common: their IP addresses were exposed.
Users could try to hide IP addresses with Tor or a VPN; however both of these strategies have serious weaknesses.
The Tor network has "semi-trusted" Directory Authorities which give a handful of Tor node operators overreaching influence into network consensus.
Network consensus ultimately determines who is allowed to relay traffic on the Tor network based on the views of the Authorities.
Furthermore, correlation attacks are possible with VPNs, making it easy for large attackers to de-anonymize a user's traffic.

So what can Alice, Bob, Charlie, and Dave do to mitigate these threats? Well, they could simply use Kovri!
With Kovri, nodes will no longer be able to see IP addresses, making passive surveillance tactics impractical.
Furthermore, the source of solved blocks are unknown when transmitted through Kovri, which will substantially improve Monero's censorship resistance.

As you can see, Kovri is a software that allows users to send transactions more privately and anonymously than ever before.
Let's next go over some technical details to have a better understanding of how Kovri works under the hood. 

## 5) Kovri and Technical Attributes

Kovri tunnels traffic through the I2P network utilizing “garlic encryption” and “garlic routing”.
Information travels within a private overlay-network by way of messages, which are encrypted in layers each time the message is passed along to peers in the network, similar to a Matryoshka doll.
For each inner doll there is a lock and public key to the next doll.
Peers in the network are not able to read the contents of the message being relayed, so information sent from the sender to its destination (and vice-versa) are secured.
The only information visible to peers is the instruction for sending messages to the next peer.
To achieve greater privacy at a slight cost to performance, users are able to connect to several peers.
Essentially, Kovri covers an application's internet traffic to make it anonymous within the network.

## 6) - Conclusion

Kovri will revolutionize peer-to-peer connections and increase network resiliency and privacy worldwide.
Malicious nodes can no longer threaten users who create transactions or block them from propagating across the network.
Kovri will come bundled with future Monero releases and be enabled by default.
In addition, Kovri will feature a common API that would allow other cryptocurrencies and applications to use it, not just Monero.
For instance, chatting over IRC or visiting eepSites via the I2P network will be possible with Kovri APIs.

To learn more about Monero and the Kovri project, check out getmonero.org. and getkovri.org.
