The Kovri Script

Until this point, this video series has covered how Monero obfuscates information stored on the blockchain.
Ring signatures obscure the sender.
Stealth addressing prevents anyone, other than the sender and the recipient, from knowing that the recipient owns Monero.
RingCT hides the amount of Monero that's transmitted.
However, some personally identifiable information will still be leaked when making a transaction.
This video focuses on the technology that closes this gap of privacy. This technology is called Kovri.

Suppose Alice wants to send a transaction to Bob.
She generates a transaction on her local device and gets ready to broadcast it to the network, so it can be included in the next block.
Alice only connects to a small portion of the nodes on the Monero network. Her transaction request will need to reach as many nodes as possible - ideally all of them - for her transaction to have the greatest chance of being included in the next block.
Let's say she connects to five other nodes. We'll call each node "Bob". Once connected, she broadcasts her transaction to all five Bobs.
These nodes then forward her transaction to all the nodes they are connected to, and so on, until many (or all) nodes have this transaction.

Unfortunately, Alice takes a risk when broadcasting her transaction.
Some of the nodes on the network may be logging the IP addresses they get when transaction requests are given.
An IP address is like a home address for the internet.
Attackers will try to associate transactions with the IP addresses they originate from.
They do not know anything about what address a transaction is coming from, where it is going to, or what the amount is.

However, an attacker with enough resources could knock on Alice's door and demand that she tell them this information.
Alternatively, they could purposefully attempt to block her transaction from being broadcast to the rest of the network.

So what can Alice do to mitigate these threats? Well, she can use Kovri!

Kovri is a free, decentralized, anonymity technology developed by Monero.
Currently based on the Invisible Internet Project's open specifications, Kovri uses both garlic encryption and garlic routing to create a private, protected overlay-network across the internet.
This overlay-network provides Alice and Bob with the ability to effectively hide their geographical location and internet IP address.
Essentially, Kovri *covers* an application's internet traffic to make it anonymous within the network.
Kovri is lightweight, security-focused, and fully compatible with the I2P network.

If Alice sends her transaction with Kovri, nodes that log Monero traffic will no longer see her internet IP address, rendering passive surveillance tactics close to useless.

Now let’s imagine a different scenario.
Suppose Alice has an internet service provider that does not want her to use Monero, and send her a warning to cease and desist.
Alice can optionally send all the Monero sync data, not just the transaction broadcast, through Kovri.
Now, her Monero connections are hidden from her ISP.
This improves Monero's censorship resistance, since other people no longer know who is running a Monero node, and others cannot demand that these nodes be shut down.

Let’s look at one last scenario.
Suppose Charlie is the operator of a mining pool that controversially donates a portion of the block reward to a political party.
Other nodes could purposefully reject his solved blocks to express their disagreement with this policy.
This sort of attack is called a Sybil attack.
However, if Charlie can send his solved blocks through Kovri, then no one can censor the work from his pool, since they no longer know that his pool created it.

Kovri will come bundled with future Monero releases, and it will be enabled by default to broadcast the transaction anonymously.
Kovri will feature a common API that can be used by any cryptocurrency, not just Monero.

In summary, Kovri is a software that allows Monero users to send transactions more privately and anonymously than ever before.

Malicious nodes can no longer threaten users who create these transactions or block them from propagating across the network.
Kovri will revolutionize peer-to-peer connections and increase network resiliency and privacy worldwide.

To learn more about Kovri, go to getkovri.org. To learn more about Monero, the cryptocurrency behind this project, go to getmonero.org.
