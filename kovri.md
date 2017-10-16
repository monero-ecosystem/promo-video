## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all. In this video, we will focus on an anonymity technology, called Kovri.

## 2) - Technology recap

Up to now, we have covered how Monero obfuscates information stored on the blockchain.
Ring signatures obscure the sender.
Stealth addresses prevent outside observers from knowing the receiving address.
And RingCT hides the amount of Monero that's transmitted.
However, some personally identifiable information may be leaked at the network level when making a transaction.
This privacy leak is addressed with technology called Kovri.

## 3) - The Term - Kovri

Kovri is a free, decentralized, anonymity technology based on I2P's open specifications.
Kovri uses both encryption and sophisticated routing techniques to create a private overlay-network across the Internet.
This protected overlay allows users to hide their geographical location and IP address, essentially making Internet traffic anonymous.
An IP address is like a home address for the Internet, so this is quite sensitive information, to say the least.
Let's go through a few scenarios to see how this lightweight, security-focused software helps strengthen the unique privacy properties of Monero.

## 4) Examples

Suppose Alice wants to send a transaction to Bob, and she beings the transaction.
In order for her transaction to have the greatest chance of being included in the next block, she needs to reach as many nodes as possible.
Alice connects to five nodes and these nodes then forward the transaction to other nodes, which in turn rebroadcast it repeatedly until many (or all) nodes in the network have this transaction.
Unfortunately, Alice takes a risk when broadcasting her transaction.
Some nodes may be logging IP addresses when transaction requests are received.
Even though wallet addresses and the amount of Monero remain private, an attacker with enough resources could attempt to associate transactions with IP addresses to determine where transactions originate from.
This could potentially lead to an attacker knocking on Alice's door or blocking her transaction from the rest of the network.
So what can Alice do to mitigate these threats? Well, she can use Kovri!
If Alice sends her transaction with Kovri, nodes will no longer see her IP address, making passive surveillance tactics impractical.

Now let’s imagine a different scenario.
Suppose Charlie wants to support the Monero network by running a full node at his home.
After a few weeks, he receives a cease and desist letter from his Internet Service Provider informing him that running a node is a violation of the terms of service.
Charlie could have avoided this situation in the first place by anonymizing his Internet traffic with Kovri.
Kovri substantially improves Monero's censorship resistance by making it even more difficult to detect and shut down nodes.

In our last scenario, suppose Dave is an operator of a mining pool that donates a portion of block rewards to a political party or controversial cause.
Other nodes could purposefully reject his solved blocks to express their disagreement with his political views.
However, if Dave can send his solved blocks through Kovri, then no one can censor the new blocks created by his pool, since the source of solved blocks are unknown.

As you can see, Kovri is a software that allows users to send transactions more privately and anonymously than ever before.
Let's next go over some fairly technical stuff to have a better understanding of how Kovri works under the hood.

## 5) Kovri and Technical Attributes

Now hold on, since we are about to overview how Kovri works.

Kovri is currently built from I2P's open standards. I2P stands for the invisible internet protocol. Kovri acts as an anonymizing router as it tunnels traffic through the I2P network.

To protect their anonymity, each participant connects to other network members and uses them to pass messages.
In most circumstances, people will choose four peers: two for incoming connections, and two for outgoing connections.
People can use more for greater privacy at the cost of performance.

Suppose Dave's mining pool has just solved a block and would like to send this transaction information to the other network members.
Dave's router will send the message to his two outgoing peers, who will then search for the incoming peers of other nodes on the network.
Dave can commincate securely without other Monero nodes on the network knowing what his actual IP address is.
The other participants in the I2P network do not know what their place is in the chain of routing, nor do they know what information is being relayed inside the network.
This is called garlic routing, wherein the only information shown to peers is the instruction set for sending to the next peer.

## 6) - Conclusion

Kovri will revolutionize peer-to-peer connections and increase network resiliency and privacy worldwide.
Malicious nodes can no longer threaten users who create transactions or block them from propagating across the network.
It will come bundled with future Monero releases and be enabled by default.
Kovri will also feature a common API that would allow other cryptocurrencies and applications to use it, not just Monero.

To learn more about Monero and the Kovri project, check out getmonero.org. and getkovri.org.
