## History:
initial, Scoob (Apr. 2017)

SamsungGalaxyPlayer - b0eefaa

JM - implementing kenshi84's comments - ac43af6

SamsungGalaxyPlayer - 0c27e6a

Scoob - f8f54ad

ajs - 018f931

JM - this one - minor fixes

## 1) - Intro

Monero is secure, untraceable, electronic cash. It is open-source, decentralized, and freely accessible to all.
In this video, we will focus on Ring Confidential Transactions, commonly known as RingCT.

Monero 是一種安全且無法追蹤的電子加密貨幣。它來自一個開放原始碼、去中心化且任何人皆可自由參閱的開發專案。
在這個影片中，我們要來談談環狀簽名保密交易，通常簡稱為環簽交易(RingCT)。
 
## 2) - Technology recap
 
In our last video, we illustrated how Monero ring signatures protect senders' privacy by preventing transaction inputs from being distinguishable from one another.
This is accomplished by the use of digital signatures, where there is an actual signer hidden among multiple ring members to authorize a transaction.
Additionally, we learned that key images are used to prevent Monero inputs from being spent more than once.
Ring signatures ensure privacy of the sender, since inputs are untraceable.
To increase the privacy of both parties in a transaction, RingCT was implemented to hide transaction amounts.

在上一部影片中，我們呈現了 Monero 是如何藉由創造無法區分的交易輸入以保護付款者的隱私。
過程中使用了數位簽名的技術，將真正的交易簽署者隱藏在數個環簽輸入中完成一筆交易。
另外，我們也闡述了金鑰映像(key image)是如何用來防止交易輸入被重複花費。
因為輸入是無法追蹤的，所以環狀簽名確保了付款者的隱私。
然而為了更徹底的增加交易雙方的隱私，環簽保密交易(RingCT)被用來隱藏交易的金額。


## 3) - The build-up to Ring CT

Prior to the implementation of RingCT, Monero required transaction amounts to be split into specific denominations.
For example, an output of 12.5 Monero would be broken up into three separate rings in the amounts of 10, 2, and 0.5.
This technique ensured that there would be ample ring members, since a ring signature could only ring together outputs of the same value.
However, a downside to this process is that an outside observer was able to see the amounts transacted.
To address this shortcoming, Monero activated RingCT in January 2017.
RingCT prevents privacy leaks by hiding transaction amounts in the blockchain.
A month after RingCT was activated, approximately 98% of new transactions were using the RingCT protocol.
After September 2017, the use of RingCT will be mandatory for all Monero transactions.

在 Monero 開始啟用 RingCT 之前， Monero 的交易金額需要先分割成特別的單位數量。
譬如，一筆金額為 12.5 的交易輸出會被分割成三筆分別為10、2、0.5的金額。
這樣的方式可以讓環狀簽名在建構時可以有足夠等同的輸入來源，因為環狀簽名的輸入金額必須是一致的。
但在這個交易步驟中，每一筆交易金額都是可見的。
為了改善這個缺點， Monero 在 2017 年的一月啟用了 RingCT 的功能。
在啟用 RingCT 的一個月後，大約有 98% 的交易都是使用 RingCT 的協定。
而在 2017 年的九月之後，所有的 Monero 交易都會是強制使用 RingCT 協定。


## 4)  RingCT Non-Technical Attributes

Today with RingCT, newly created Monero firstly resides in outputs that have visible amounts.
When new Monero is transferred for the first time, RingCT outputs with masked amounts are generated.
As a result, transactions no longer need to be broken down into different denominations.
This means that a wallet is free to pick ring members from any RingCT outputs, which significantly improves privacy.
It should be noted that Monero ring signatures can't include both pre-RingCT outputs and masked RingCT outputs in a single ring, so - like newly created Monero - a pre-RingCT output must first be converted to a RingCT output before it can be included in a ring signature with other RingCT outputs.
Let's walk through an example, and then take a deep dive to see how RingCT works.

如今使用 RingCT 的協定下，每個新產生的 Monero 會以可見金額的形式存在於交易輸出中。
當這些新產生的 Monero 在第一次被轉移時，將會產生帶有金額遮罩的 RingCT 交易輸出。
如此一來， Monero 的交易將不再需要被分割為特定的單位數量。
這代表著錢包在交易時可以任意挑選一個 RingCT 的交易輸出，這大幅提高了匿蹤性。
值得注意的是，一個環狀簽名裡無法同時包含在 RingCT 啟用前的舊交易輸出與帶有金額遮罩的新交易輸出。
所以就如同新產生的 Monero 的處理方式，在 RingCT 啟用前的舊交易輸出必須要先轉換成 RingCT 的交易輸出，接著才能與 RingCT 的輸出形成環狀簽名。
讓我們來舉個例子，再來仔細解釋 RingCT 技術是如何運作的。

## 5) – RingCT Transaction, and Technical Attributes

Alice has an output of 12.56 and would like to send Bob 2.5 Monero.
Since outputs can't be spent twice, Alice needs to spend the output in its entirety and return the change to herself.
So, Alice's transaction would have one input of 12.56 Monero and 2 outputs - one that is 2.5 Monero designated for Bob and another that is 10.06 Monero, which is sent back to her wallet as "change" of the transaction.
To prove that Monero has not been fraudulently fabricated in a transaction, the sum of a transaction's inputs must equal the sum of its outputs.
Due to cryptographic properties of RingCT, Alice is required to "commit" to the amount of an output, revealing just enough information for the network to confirm the transaction, while not publicly disclosing the amount she is spending.
Although commitments look like random numbers, miners are still able to confirm that the amount of Monero being sent to Bob is the same as the amount of funds available. [See Note 1]
Another important aspect of a RingCT transaction is the "range proof", which prevents senders from committing to negative values in order to secure the supply of Monero.
A range proof cyptographically proves the amounts used in a transaction is greater than 0 and less than some arbitrary number.
While an outside observer is unable to see the actual amounts in outputs of a transaction, they are able to confirm that the transaction is a legitimate one that the network should accept.

舉例來說，Alice 擁有一個金額為 12.56 的交易輸出並想付款 2.5 個 Monero 給 Bob。
由於輸出是無法被花費兩次的，所以這個輸出將會被整筆花費出去，之後才會將找零返回給 Alice 。
以這個例子來說， Alice 的這筆交易將會有一筆 12.56 Monero 的輸入和兩筆輸出，第一個輸出會是要付款給 Bob 的 2.5 Monero ，而另一筆將會是 10.06 Monero 的找零將會傳送回她原本自己的錢包。
為了防止 Monero 在交易的過程中被偽造而無中生有，每一筆 Monero 的交易輸入與交易輸出各自的金額總和必須相同。
而因為 RingCT 的特性， Alice 會被要求提供此筆交易輸出的金額，僅提供讓交易網路可以驗證此筆交易的資訊，而不公開實際上到底花費了多少金額。
儘管提供的這些資訊看起來像是隨機的數字，礦工們仍然可以從這其中驗證轉帳給 Bob 的金額與可用的餘額相同(詳見註1)。
在 RingCT 交易中，另一個重要的機制是"範圍保護"，這個可以防止有人提交了負值的交易金額，以保護 Monero 的發行量。
範圍保護在加密學上保證了交易中的金額是大於零並小於特定的數字。
因此即使外部觀察者的角度無法從交易輸出中得知真正的交易金額為何，他們依舊可以驗證此筆交易為有效的。

## 6) - Conclusion

As a result of Monero's baked-in privacy features, users are able to transfer Monero to whomever they like; and no one would know how much was sent nor who the sender or recipient were.
These qualities make Monero a leading privacy-centric digital currency, but the innovation doesn't stop there.
In our next video, we'll discuss Kovri, a C++ I2P router that will make Monero transactions more secure than ever before.

拜 Monero 所植入的隱私功能所賜，使用者可以隨意地發送給任何對象，而不用擔心有人會得知交易的金額或是交易雙方的身分。
這些特性使得 Monero 成為在保護隱私需求中最先進的數位貨幣，但這些創新的腳步不會停歇於此。
在下一部影片中，我們將討論 Kovri ，一個用 C++ 打造的 I2P 路由技術，將使得 Monero 的交易更加安全。

## 7) - The end

If you are interested in what makes Monero the leading privacy-centric cryptocurrency, please check out the other videos or visit getmonero.org.

如果你有興趣了解是什麼讓 Monero 成為最重視隱私的加密貨幣，請參閱我們其他的影片或參閱 getmonero.org。

--------------------------------------------------

Note 1. The following could be reflected on-screen in the commitments section, but should not be narrated.

This commitment takes the form of this formula (rct = x*G + a*H(G)).
The two most important variables to consider here are a and x.
H(G) and G are dependent on many other factors that are out outside this video's scope.
a is the actual amount being sent in the transaction, in this case 2.5.
x is a random number acting as a mask, which your wallet software will generate automatically.
In the simplest sense, we can rewrite this equation as rct = a random value + a real value.

You can publish the value 'rct' to the rest of the network as an output, and the network can use this to verify that your transaction is legitimate. This can be used to verify the sum of the inputs used in the transaction equals the sum of the outputs.
However, since an outside observer does not know what the variable x you generated earlier is, he has no way of knowing how much was spent in the transaction.

註1: 

交易中提供的資訊由這個公式而來: rct = x*G + a*H(G) 。
在這邊最重要的變數為a與x。
H(G)和G是關係到許多在這部影片所述之外的因素。
a是在交易中的真正金額，在影片中的例子也就是2.5。
x是用來作為金額遮罩的隨機數字，由錢包所自動產生。
簡單來說，這個公式可以被簡單敘述為 rct = 隨機數字 + 真正的交易金額。

你可以發佈rct的值到交易網路中作為一個交易輸出，而網路將可使用這個值去驗證你的交易是否有效。這個值可以被用於驗證交易輸入是否等於交易輸出的金額。
然而，對於一個外部的觀察者來說，並無從得知變數x的實際金額，所以無法得知有多少金額在交易中被實際的花費掉。