# Safe Havens - An Apocalypse Checker
Safe Havens is a conceptual blockchain art project created on [Bitcoin Ordinals](https://docs.ordinals.com/inscriptions.html) and distributed via [Bitcoin Runes](https://docs.ordinals.com/runes.html).

## **The Concept**

Safe Havens is an HTML program that checks the availability of 20 websites deemed \*very safe\* in terms of longevity by GPT-4.

If all of these websites fails to connect, the program returns with the following message:

*\> APOCALYPSE*

*\> Nothing really ever mattered.*

*\> Your existence is\
\> as unimportant as always.*

![Output when all the websites are unavailable](https://images.mirror-media.xyz/publication-images/HFd5Q9_XjGRX1OtKi7KJa.png?height=1330&width=679)

If any of the safe havens are still available, the program redirects the viewer into the website.

![Output when any of the websites are available](https://images.mirror-media.xyz/publication-images/MLXdjY1MafYuhi-IkbKi7.png?height=262&width=831)

## **How Does It Work?**

Safe Havens is a very simple [HTML](https://en.wikipedia.org/wiki/HTML) program that uses [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) to fetch website availability.

![First 57 lines of Safe Havens](https://images.mirror-media.xyz/publication-images/kydgehCFRi8-SzBtP2MHT.png?height=1368&width=1131)

It starts by shuffling the domain array so that the program can test a different domain on each run. After that, when the content is loaded, it checks Safe Havens one by one.

Each check consists of a simple [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) call with [no-cors mode](https://developer.mozilla.org/en-US/docs/Web/API/Request/mode#no-cors) and a 3-second timeout. If the call is successful, the program redirects the viewer to the checked website, if the call is failed, the program tries to check the next website in the domains array. If all calls fail, the program returns the apocalypse message.

## **GPT-4 Conversation**

GPT-4 is famous for its shallow answers and the question of “What are some websites that would still be reachable after 100 years?” is a very superficial one. So I used GPT-4 as a a common knowledge hub to get an answer without adding any personal bias.

![The Conversation I had with ChatGPT](https://images.mirror-media.xyz/publication-images/OaQp9O8XvPcG1JRSHlyfM.png?height=1131&width=939)

## **Use of Bitcoin Ordinals and Runes**

Safe Havens is stored on Bitcoin as an inscription via the Ordinals protocol. This is because the artwork needs to stand the test of time to do its job. And since Bitcoin is seen as the safest haven in the universe (at least by me), I chose to store the art on Bitcoin.

As a distribution method, I chose Bitcoin Runes, a new experimental protocol on Bitcoin that can act as [fungible tokens](https://en.wikipedia.org/wiki/Fungibility), or as [semi-fungible tokens](https://www.coindesk.com/tech/2021/08/17/what-is-a-semi-fungible-crypto-token/) as the way used in this project.

### **Use of Runes**

Bitcoin Runes has a [few launch parameters](https://docs.ordinals.com/runes/specification.html#runestones) that make this artwork use Runes as a distribution mechanism.

**Name:** The name of the Runestone has been set as [ALL•YOUR•SAFE•HAVENS](https://ordinals.com/rune/ALL%E2%80%A2YOUR%E2%80%A2SAFE%E2%80%A2HAVENS).

The names can be between 12 and 26 characters at the time of writing. As more time goes by, runes with fewer characters can be etched/deployed.

**Divisibility:** This is the most important parameter since setting it to 0 makes the token actually Semi-Fungible. This way, the token acts similarly to a single [ERC-1155](https://ethereum.org/en/developers/docs/standards/tokens/erc-1155/) token of Ethereum.

**Premine:** This setting allocates a certain amount of tokens to the deployer. It is set to 0, which means no artist allocation (although it doesn’t mean I won’t mint some after launch 👀)

**Terms:**\
\- Amount: Set to 1 to make sure everyone can mint one token per transaction.\
\- Cap: Set to 100 to make sure a total of 100 tokens can be minted, ever.\
\- Height: Set as “843630, 8436300” to make the token start minting at block 843630 and end minting at 8436300.

**Symbol:** Each rune comes with a symbol parameter. This sets how the amounts of tokens should be displayed.

For Safe Havens, the symbol is set as: [🧿](https://en.wikipedia.org/wiki/Nazar_\(amulet\)). This is the symbol of the Nazar amulet. It is known to give protection from the [evil eye](https://en.wikipedia.org/wiki/Evil_eye). It is a symbolic choice to protect our Safe Havens from the evil eye.

The project started as an experiment to leave a mark on this shiny new protocol that its future and longevity are very much unknown. A small mark beside thousands of meme coins and highly speculative, [degenerate plays](https://runepunks.xyz/).

![Some Early Rumblings about \"Art on Runes\" in Pushers Discord](https://images.mirror-media.xyz/publication-images/JkruUQEehV60R7Poz34cz.png?height=1625&width=1080)

## **Future-Proofness**

The artwork speculates to exist even after 100 years. Because of this, the code has been created as simply and as understandable as possible. Safe Havens consists of 188 lines of code, a mix of HTML, CSS, and JavaScript languages.

### **JavaScript-less-ness:**

It seems like a stretch but Safe Havens is prepared for a future where there is no default support for JavaScript. Browsers with JavaScript disabled will see the below error:

![Safe Havens on a JavaScript disabled browser](https://images.mirror-media.xyz/publication-images/iK8iAreLoLNqWmRCcY3Q2.png?height=580&width=957)

### **HTML-less-ness:**

If we go even further, we can think about a future with no HTML support. To be prepared for that case, the first 7 lines of the code come with the following explanation:

![The first 7 lines of Safe Havens](https://images.mirror-media.xyz/publication-images/hAvCZ4FmkP3wNKMHHU26Y.png?height=204&width=1387)

One step further might be the absence of the Ordinals protocol or Bitcoin itself. In that case, the only hope for Safe Havens is the hope of a hard disk being found in the ruins of its used-to-be location.

## **Getting Rugged by Content Security Policy**

Safe Havens can’t be properly experienced using the official Ordinals website since the [ord client](https://github.com/ordinals/ord) adds a safety feature to its server called [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP).

This basically prevents any call outside of the server and results in every Safe Haven being seen as down.

However, ord client is only a way of displaying inscription on Bitcoin Ordinals protocol. You can properly experience Safe Havens on its [GitHub Page](https://ygtdmn.github.io/safe-havens/) or by running [the program](https://github.com/ygtdmn/safe-havens/blob/main/index.html) on your computer.

## **How to Mint?**

You can mint a token by [spinning up your own Bitcoin node](https://bitcoin.org/en/full-node) and [installing Ord client](https://github.com/ordinals/ord/blob/master/README.md) or use third-party tools such as [Luminex](https://luminex.io/runes/mint?rune=ALL%E2%80%A2YOUR%E2%80%A2SAFE%E2%80%A2HAVENS) and [OrdinalsBot](https://ordinalsbot.com/runes) to mint easily.

Mint will start at block 843630, approximately around May 14th, 2024. There is no mint price (free mint) as it’s not a thing on Bitcoin Runes.

Trading runes is a highly speculative and most likely dangerous game. If you are planning to mint, please wait for gas to be lower to not spend any unnecessary fees to miners.

## **Final Words**

Even though people have been [creating art on Bitcoin](https://messagesfromthemines.brangerbriz.com/) [for years](https://medium.com/kaleidoscope-xcp/the-early-evolution-of-art-on-the-blockchain-part-1-d52d1454e34b), after the launch of the Ordinals protocol, Bitcoin saw a huge surge of artists creating on it. I also created a small collection on the first week of Ordinals called [BitGrids](https://twitter.com/YigitDuman/status/1765435184499814828).

It’s amazing to see Bitcoin, the biggest decentralized public ledger continues to give more opportunities to create and host art.

Until next time,

Yigit