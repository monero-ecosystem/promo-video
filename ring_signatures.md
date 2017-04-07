## History:
initial, Scoob (Nov. 2016)

---

##Ring Signatures Script

1 
00:01:00 --> 00:06:00
Monero is a secure, private, untraceable currency. 
It is open-source and freely available to all.


2 
00:06:00 --> 00:10:00
In this video, we will explain Monero's 'Ring Signatures'.


3
00:10:00 --> 00:13:17
Monero uses Ring Signatures to obscure where a transaction came from, by hiding the true source amongst multiple decoys.


9
00:27:00 --> 00:28:00
Let’s walk through an example transaction.


10
00:29:00 --> 00:32:00
Alice sends Bob 100 XMR with 4 decoys, using 80 and 20 XMR “bills”  
Or, “Alice sends Bob some Monero in a transaction with 4 decoys”
(video can list “mixin = decoys”, perhaps)
(are we going to talk about pre-RCT stuff, or post-RCT? Because the videos will be released post-RCT, and denomination stuff will be deprecated at that point)
*(I think it would be helpful to reflect the denomination stuff.  It provides context.  It reflects the opaquity of the blockchain prior to RCT)*
Really, if we can avoid mentioning the amount at all, it would be best. This is just showing how the origin is hidden, not the amount, amount in this context (while relevant) doesn’t add a ton to the content we’re trying to convey

11
00:32:00 --> 00:35:00
To an outside observer, 80 XMR and 20 XMR are transferred from one of possible accounts to another.
For a RingCT transaction, an outside observer is unable to view the amount being sent.




13
00:35:00 --> 00:37:00
Along with each denomination are four equal denominations of each. 


14
00:35:00 --> 00:37:00
That is, it appears that each of the three amounts, 100, 20, and 3, could be coming from any of five possible senders.


13
00:37:00 --> 00:40:00
Eve, who is an external observer, doesn’t know the real amount of this transaction



14
00:40:00 --> 00:43:00
Now, Bob is sending that 3 XMR output to Charlie, 


15
00:43:00 --> 00:45:00
the privacy hasn’t been broken.


16
00:45:00 --> 00:48:00
But lets say Bob wants to send Charlie 23 XMR, 


17
00:48:00 --> 00:51:00
and chooses 20 and 3 outputs were used in Alice’s transaction. 


18
00:51:00 --> 00:53:00
Now, the privacy has been threatened. 


19
00:53:00 -->00:56:00
Because Alice sees two outputs  created in the same 	transaction being used in another, 


20
00:56:00 -->01:00:00
she might infer that those two outputs likely belonged 
to the creator of that transaction, Bob. 

	
21
01:00:00 -->01:03:00
An external observer doesn’t know the identities of Alice and Bob, but can also infer those 		outputs were real.
	
22
01:03:00 --> 01:08:00
Also, it means that likely the other outputs involved didn't belong 
to Bob and weren't actually spent in the transaction.


23
01:08:00 --> 01:10:00
Here Ring Confidential Transactions come into play.


24
01:10:00 --> 01:13:00
When you send a transaction using traditional ring signatures


25
01:13:00 --> 01:15:00
your sum split into smaller outputs,


26
01:15:00 --> 01:18:00
that ought to be mixed with others of same denominations


27
01:18:00 --> 01:21:00
Ring Confidential Transactions allows sender to hide the amount of the transaction. 


28
01:21:00 --> 01:25:00
This means, Alice’s transaction would have only 2 outputs: 


29
01:25:00 --> 01:27:00
the output she was actually going to send Bob, 


30
01:27:00 --> 01:30:00
and the change sent back to her 


31
01:30:00 --> 01:35:00
And Bob only knows Alice received change, but he doesn’t know the amount. 

32
01:35:00 --> 01:39:00

Now Bob can’t use 2 outputs from previous transaction, because he received only one single output.


33
01:39:00 --> 01:44:00
This is how Ring Confidential Transactions make Monero The most private cryptocurrency ever.


34
01:47:00 --> 01:63:00
For more information about Monero, 
visit Getmonero.org