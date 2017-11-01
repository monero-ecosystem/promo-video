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

## 4) Examples

Let's go through a few scenarios to see how this lightweight, security-focused software helps strengthen a user's privacy.

Suppose Alice wants to send Monero to Bob.
Alice's wallet creates a transaction and then broadcasts it to the Monero network.
The Monero network is made up of nodes that communicate with each other by directing messages using IP addresses.
This means that it might be possible to geographically trace data as it travels over the open Internet, from start to finish and everywhere in between.
Even though the sender's and recipient's wallet addresses - as well as the amount of Monero sent - remain private, Alice is taking a risk in broadcasting her transaction as some nodes may be logging IP addresses.
An adversary with enough resources could attempt to associate transactions with IP addresses to determine from where transactions originate.
This could potentially lead to an adversary not relaying her transactions to the rest of the network; or - worse - arriving at her front door.

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

So what can Alice, Bob, Charlie, and Dave do to mitigate these threats? They could use Kovri!
If they exclusively use Kovri to connect to the Monero network, no one will know their IP address, making passive surveillance impractical, while substantially improving Monero's censorship resistance.

As you can see, Kovri is a software that allows users to send transactions more privately than ever before.
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
