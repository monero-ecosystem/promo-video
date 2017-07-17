## History:
initial, Scoob (Nov. 2016)

ajs - 6091e9a, 39df73f, 2355e1b, beffe23, a18d8de

JM - a18d8de

Scoob - 43af275

SamsungGalaxyPlayer - 4a4e99f

ajs - a292a18 - 0aad47d

JM - f22aa69

ajs - 08ffd69

Scoob - this one

---

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on ring signatures.

Monero 是一種安全且無法追蹤的電子加密貨幣。它來自一個開放原始碼、去中心化且任何人皆可自由參閱的開發專案。
在這個影片中，我們要來談談環狀簽名。
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero stealth addresses prevent outputs from being associated with a recipient's  public address.
This is accomplished by the use of one-time destination public keys.
One-time public keys are only spendable by the recipient, and only the recipient is able to detect their designated output on the blockchain.
Since all outputs are unlinkable, the privacy of the recipient is ensured.

On the input side of the transaction, the sender's privacy is protected with the use of ring signatures.

在上一個影片中，我們討論了 Monero 是如何藉由隱匿性地址來避免交易輸出被連結到收款者的公開地址。
這是使用了一次性公鑰所達成的效果。
一次性公鑰僅能被收款者所再花費，且僅有收款者得以查看其在區塊鏈上所擁有的交易輸出。
因此所有的交易輸出都是無法被追蹤的，可以確保收款者的隱私無虞。

而在交易輸入的這端，也就是付款者的隱私，則是藉由環狀簽名(ring signatures)來保護。


## 3) - The Term - Ring Signatures, Key Image

A ring signature is a type of digital signature in which a group of possible signers are fused together to produce a distinctive signature that authorizes a transaction.
This is analogous to the signing of a check from a joint bank account, but with the actual signer remaining unknown.
The digital signature is made up of the actual signer combined with non-signers to form a "ring," where all members are equal and valid.
The actual signer is a one-time spend key that corresponds with an output being spent from the sender's wallet.
The non-signers are past transaction outputs pulled from the blockchain, which act as decoys.
These outputs together make up the inputs of a transaction.
To a third party, all of the inputs appear equally likely to be the output being spent in the transaction.
This feature helps the sender hide the origin of the transaction, by making all inputs indistinguishable from each other.


You may now be asking yourself, "if there is no way for a third party to verify which output is being spent, what would prevent someone from spending the same output twice?"
This potential issue is addressed by the use of “key images.”
A key image is a cryptographic key derived from an output being spent and is made part of every ring signature transaction.
There can exist only one key image for each output on the blockchain, yet due to its cryptographic properties, it is not possible to determine which output created which key image.
A list of all used key images are maintained in the blockchain, enabling miners to verify that no outputs are spent twice.

Let's go through an example to see how all this works.

環狀簽名是一種數位形式的簽署方式，藉由混合一群簽署者的簽名來製造一份無法分辨來源的簽名，而得以授權一份交易。
這可以類比是從一個共同銀行帳戶發出的支票，但無法得知真正的簽署者是誰。
這份數位簽名是由一位簽署者與多位非簽署者組成的"環"所簽署，每一位參與者都是同等的。
其中真正用來簽署的一次性花費金鑰，是來自於該付款者的前一筆收款交易輸出。
其餘非簽署用的數個來源是來自區塊鏈上舊有的交易輸出，作為誘餌。
這些輸出將被合成一個新的交易輸入。
從第三方的角度來看，每一個交易輸入都是相同而無法區分彼此的。
這個過程可以幫助付款者隱藏其先前的交易來源。

此時您可能會產生疑問，如果第三方無法驗證哪一個交易輸出尚未被花費，那要如何防止有人重複的花費同一筆交易輸出呢?
這種狀況可以用金鑰映像(key image)來解決。
金鑰映像是來自於交易輸出被花費時產生的一組加密金鑰，會被包含在每一筆環狀簽名的交易中。
基於加密學的原理，每一個交易輸出只會對應一個金鑰映像存在於區塊鏈上，但無法回推是哪一組金鑰映像是由哪一筆交易輸出產生。
所有的金鑰映像清單會被記錄於區塊鏈中，使礦工得以驗證交易輸出沒有被重複花費。

讓我們用一個例子來看看這是怎麼運作的。


## 4) – Ring Signatures Transaction

Alice wants to send Monero to Bob with a “ringsize” value of five. 
One of the five inputs will come from Alice's wallet, which will be consumed in the transaction.
The other four inputs are arbitrarily picked from the blockchain, and are used as decoys.
This forms a group of five possible signers, where all ring members are plausibly the actual signer of the transaction.
To an outside observer, including to Bob himself, it's not clear which input was truly signed by Alice’s one-time spend key.
However, with the key image, the network is able to securely confirm that the Monero being transferred to Bob have not been spent before.
As you can see, by using ring signatures, Monero protects the privacy of the sender by obscuring the source of inputs, and in doing so, ensures that the origin of any monero remains untraceable.

Alice 想要用環簽大小(ringsize)為5的方式付 Monero 給 Bob。
此時5個交易輸入的其中1個輸入即會是來自於 Alice 的錢包，將會在交易中被消耗。
其餘4個交易輸入則是隨意的在區塊鏈中挑選而來，作為誘餌。
這就會形成一個5個輸入的環狀簽名，每一個輸入皆有可能為真的簽名。
對一個外部的觀察者，包括 Bob 本人，都無法得知哪一個輸入才是真正來自 Alice 的一次性花費金鑰。
如此一來，藉由使用環狀簽名的技術來混淆交易輸入的來源， Monero 可以保護付款者的隱私安全，確保每一個 Monero 的來源都是無法追蹤的。


## 5) RingCT

To increase the privacy of both parties, Ring Confidential Transactions, commonly referred to as RingCT, were implemented to hide transaction amounts.
RingCT brings some improvement to the ring signture protocol.
We'll talk more about RingCT in our next video.

為了要提高交易雙方的隱私保護，環狀簽名保密交易，通常簡稱為 RingCT，被用來隱藏 Monero 的交易金額。
RingCT 為環狀簽名協定帶來了許多好處。
我們將會在下一集討論。


## 6) - The end?

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.

如果你有興趣了解是什麼讓 Monero 成為最重視隱私的加密貨幣，請參閱我們其他的影片或參閱 getmonero.org。