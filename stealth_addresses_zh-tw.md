## History:

https://paste.fedoraproject.org/533517/83578148/ - initial, JM

https://paste.fedoraproject.org/536623/ - Scoob

https://paste.fedoraproject.org/542498/14859669 - JM

lost :( 

alvinjoelsantos - commit: ee7b7e1

JollyMort - commit: f2a8892

scoobybejesus - commit: 53a5b45

alvinjoelsantos- commit: df603fd

knaccc: 3#issue-212874963

scoobybejesus: 3#issuecomment-285545922

scoobybejesus: https://paste.fedoraproject.org/paste/c6UG6HGOXIoZFeo72sZsCF5M1UNdIGYhyRLivL9gydE=

alvinjoelsantos- commit: e14a015, c7e30df, 35062ab, 807d3a0

JollyMort - commit: 3c339f7

alvinjoelsantos - commit: 4de82c2

knaccc: 3#issuecomment-286899474

scoobybejesus: 3#issuecomment-287072833

knaccc: 3#issuecomment-287086144

alvinjoelsantos - commit: 68b2ed0, 004d128, a83eaf0, 7ce43ce

knaccc: 3#issuecomment-287429402

this one

---

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on stealth addresses.

Monero 是一種安全且無法追蹤的電子加密貨幣。它來自一個開放原始碼、去中心化且任何人皆可自由參閱的開發專案。
在這個影片中，我們要來談談隱匿性地址。


## 2) - Technology recap

Let's take a step back, and recap some concepts from the previous video.
We learned that Monero uses a distributed peer-to-peer consensus network to record transaction outputs in a blockchain.
If Alice owns Monero, it means that she has exclusive control over some of these outputs.
When Alice sends Monero to Bob, Alice is announcing to the network that she wishes to transfer the value of some of her outputs to a brand new output for Bob, which only he can control.
In other words, a transaction is the transformation of old outputs belonging to one wallet into new outputs belonging to another.
Let's take this a step further, to see how stealth addresses enhance a user’s privacy.

讓我們退一步，先來回顧一下前一部影片裡的重點概念。
我們知道 Monero 使用了去分散式的點對點共識網路去紀錄區塊鏈中的交易輸出。
如果 Alice 擁有 Monero，這代表著她擁有著某些交易輸出的控制權。
當 Alice 轉帳一些 Monero 給 Bob 時，Alice 其實是在對交易網路宣布她想要把某些她可以控制的交易輸出重新打包成一個新的交易輸出並把控制權完全轉移到 Bob的手上。
換句話說，一個交易即是指，屬於某個錢包的舊交易經過轉形之後，轉移到屬於另一個錢包的新交易輸出的過程。
讓我們再更進一步，了解隱匿性地址是如何增加使用者的隱私權。


## 3) - The Term - Stealth Addresses

In every transaction, a stealth address, also known as a one-time public key, is automatically generated and recorded as part of the transaction to indicate who can spend an output in a later transaction.
An outside observer cannot tell if funds are moving from Alice to Bob nor link wallet addressees together by just looking at the blockchain.
Therefore, when Alice sends Monero to Bob, the output Bob receives will not be publicly associated with Bob’s wallet address. 
However, if Alice ever needs to prove that she in fact sent Monero to Bob, her wallet has the ability to verify that payment was sent.
Bob can rest assured that no one else can see when or if any Monero was sent to him.
If Bob were a merchant, this feature would be a great benefit, because no one can tell how many different customers he has, whether any of them are repeat customers, or if he has any customers at all.
Now, buckle your seatbelts, because we are about to go over some fairly technical stuff.

在每一個交易中，隱匿性的地址，也就是一次性的公鑰，將會被自動產生並記錄在交易之中來表明是誰在之後的交易中可以使用這些交易輸出。
以旁觀者的角度來看，並無法從區塊鏈上得知資金是否從 Alice 移動到 Bob 或是任何錢包的地址與這此筆交易相關。
因此，當Alice 轉帳 Monero 給 Bob 時，Bob 所收到的交易輸出並不會與 Bob 的錢包地址出現關聯。
但是，如果 Alice 需要證明她真的有轉帳 Monero 給 Bob，她的錢包亦可做出交易有確實傳送的的驗證。
所以 Bob 可以確信沒有其他人能夠得知這筆 Monero 的交易發生在何時或甚至是否存在。
如果 Bob 是一個商人，那這個功能就非常有好處，因為沒有其他人可以從區塊鏈上得知他的客戶組成和數量。
好了，接下來要注意了，因為我們將要深入到技術層面的解釋。


## 4) - One-time Destinations

A Monero wallet address is a 95-character string, which consists of a public view key and a public spend key.
When Alice sends Monero to Bob, Alice’s wallet will use Bob’s public view key and public spend key as well as some random data to generate a unique one-time public key for Bob’s new output. 
Everyone can see the one-time public key on the blockchain, but only Alice and Bob know that Alice sent Monero to Bob.
The output is created in such a way that Bob is able to locate the output destined for him by scanning the blockchain with his wallet’s private view key.
Once the output is detected and retrieved by Bob’s wallet, he would be able to calculate a one-time private key that corresponds with the one-time public key and spend the relevant output with his wallet’s private spend key.
This whole process occurs without ever having Bob’s wallet address publically linked to any transaction.

每一個 Monero 地址是95字元的字串，是由 public view key 與 public spend key 組成。
當Alice 轉帳 Monero 給 Bob 時， Alice 的錢包會使用 Bob 的 public view key 與 public spend key 再加上一些隨機資料來產生獨特的一次性公鑰供 Bob 的後續交易使用。
所有人都能夠在區塊鏈上看見一次性公鑰，但只有 Alice 和 Bob 自己知道他們的錢包之間有交易的發生。
當 Bob 的錢包在區塊鏈上獲取到該次的交易輸出後，錢包就能透過其一次性公鑰推算出一次性私鑰，最後就可以用 private spend key 去花費掉這些交易輸出。
這整個交易的過程完全不需要讓 Bob 的錢包地址在區塊鏈上與任何交易顯示出關聯。

## 5) - Tie-in to ring signatures

As you can see, stealth addresses prevent outputs from being associated with wallet addresses.
The sender's privacy is shielded with the use of ring signatures.
Ring signatures help obfuscate the source of outputs.
In our next video, we’ll discuss the ring signature concept in more detail and see how this feature creates untraceability in Monero.

由此你可以發現，隱匿性地址可以防止交易輸出被連結至錢包地址。
而發送者的隱私將被環狀簽名(ring signatures)所保護。
環狀簽名可以幫助混淆這些交易輸出的來源。
在下一部的影片中，我們將會進一步詳細討論環狀簽名的概念，並了解這個功能是如何讓 Monero 成為無法追蹤的匿蹤特性。


## 6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.

如果你有興趣了解是什麼讓 Monero 成為最重視隱私的加密貨幣，請參閱我們其他的影片或參閱 getmonero.org。