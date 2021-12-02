# Ripple Case Study
## A Case Study on Ripple
![Ripple](https://upload.wikimedia.org/wikipedia/commons/thumb/8/88/Ripple_logo.svg/1280px-Ripple_logo.svg.png)
### Overview and Origin
---
Ripple was conceived by Jed McCaleb and built by Arthur Britto and David Schwartz who then approached Ryan Fugger. Fugger had developed a system called OpenCoin which would transform into Ripple, a real-time gross settlement system, currency exchange and remittance network created by Ripple Labs Inc. The company also created its own form of digital currency referred to as XRP to allow financial institutions to transfer money with negligible fees and wait-time. Initially resleased in 2012, the technology was adopted by several banks as a messaging and payment system. It has recieved scrutiny from the SEC over raising over $1 billion in funds from investors by selling it's XRP token which is described as an unregistered security.
### Business Activities
---
The major financial problem Ripple is trying to solve is how payments are transacted between banks. The banking system currently uses a payment network called SWIFT which can be slow and is opague. Ripple's payment network which is based on a blockchain-like protocol is much more transparent, secure, and fast which many view as an improvement on the current system, even though it is not fully decentralized. The size of the market that Ripple is disrupting is in the quadrillions of dollars per year. According the US Treasury, SWIFT handles about $5 trillion per day, or given about 250 business days per year, about $1.25 quadrillion dollars a year. Similarly, CHIPS handles about $400 trillion per year, and Fedwire handles around $900 trillion per year (most of both of these arise out of SWIFT messages). These transactions make up a large fraction of electronic transactions in the world, so it's safe to assume that the global total isn't much more than a few quadrillion dollars a year. There is plenty to gain for Ripple / XRP.

The main technology Ripple offers that it's competitors don't is blockchain. It has it's own unique consensus protocol which ensures that payments aren't double-spent:

>Trust-Based Validation
>
>The core principle behind the XRP Ledger's consensus mechanism is that a little trust goes a long way. Each
>participant in the network chooses a set of validators, servers specifically configured to participate actively in
>consensus, run by different parties who are expected to behave honestly most of the time. More importantly, the set
>of chosen validators should not be likely to collude with one another to break the rules in the exact same way. This
>list is sometimes called a Unique Node List, or UNL.
>
>As the network progresses, each server listens to its trusted validators³; as long as a large enough percentage of
>them agree that a set of transactions should occur and that a given ledger is the result, the server declares a
>consensus. If they don't agree, validators modify their proposals to more closely match the other validators they
>trust, repeating the process in several rounds until they reach a consensus.
>>![diagram](https://xrpl.org/img/consensus-rounds.svg)

Ripple also makes it easy to access the XRP Ledger from any webpage by loading xrpl.js in that page's HTML. For example:
```
<script src="https://unpkg.com/xrpl@2.0.0/build/xrpl-latest-min.js"></script>
```
Once that is setup, running the code below will return the latest ledger version and a list of transactions that were newly-validated in that ledger version
```
async function main() {
  const api = new xrpl.Client('wss://xrplcluster.com');
  await api.connect();

  let response = await api.request({
    "command": "ledger",
    "ledger_index": "validated",
    "transactions": true
  });
  console.log(response);
}
main();
```
Here is the output:
```
{
  "id": 0,
  "result": {
    "ledger": {
      "accepted": true,
      "account_hash": "F7CC36000EE8B3FA78EF4A01EC0B6789FAB6655033A0F53CBE708DEB38674256",
      "close_flags": 0,
      "close_time": 691784102,
      "close_time_human": "2021-Dec-02 18:15:02.000000000 UTC",
      "close_time_resolution": 10,
      "closed": true,
      "hash": "B7D02C71869B280992E1F7868512ECDAA0325C968DC9BC8DC0924067CDB76BF7",
      "ledger_hash": "B7D02C71869B280992E1F7868512ECDAA0325C968DC9BC8DC0924067CDB76BF7",
      "ledger_index": "68083439",
      "parent_close_time": 691784101,
      "parent_hash": "F4EFE322DCB4B4011F82166F4EAC54E24B7BEFF8176D2CB7571DEC8FD11895CB",
      "seqNum": "68083439",
      "totalCoins": "99989981548913615",
      "total_coins": "99989981548913615",
      "transaction_hash": "724CA951450E036B8F14D97673AA1D0BEA25961EEEC8354E2BB584D295C41582",
      "transactions": [
        "054AB10D9FEA4F479A2F360F879BD13D1C4E51053BBE9CD59CF18A944510A507",
        "14EBE09CEB7A9CC064BE9CF52A726C88B380C8C238FBFA3E048A138B77EDD9BE",
        "1F678BB105F11D04805E64921744A09EDC9140435D35326D8FC5488FDB569D0B",
        "289839E8E4ED0443A9F72488F7499065419BFB213C66CEB18AAF5ACE9E35CF6F",
        "297FBD4A7E93408C640E90EA6D9C6373CA78C4C2CFE2BBF709ED3EEDD83CA605",
        "2A3107A75B71AB4C86BF42357E16DAA4BAD9ECAD59FA8ADA73B7F5C0AD9A79B4",
        "2B8DB939E8E1BE872B3E16223E5570916649AA00FC5F53327B380B6EF11588C3",
        "2C8EC8B7F0342019ECE71685073617219E00C939F0E35C2E1F82890A438F7C40",
        "2E8954BB9595BB444E1D99099FBCACAA310CAD9ECED1BBA0C891234D98BFC6B5",
        "33C1D3316FB63E015ABDC4EA53BE727281EC5E982E830E5CC127A5BE0E3821DE",
        "3EA5AF701E8843DB8A4E1CA8F2E3D68B353DA2E7A602116D55FBD8DE7C9CF5D3",
        "41537EBA78F9CAB33C454BF79734D44697AF1AF141A6F0AB85BF5D6F24ABAE31",
        "44DC2B50A697F1CB89B1CD3FCE878B88172B08DA5C98FD48B93CC7BD1936ABE2",
        "47F016F99241A5917A79614F538DB46EB78B952485B66A87D2DEB599BA21B573",
        "49C7F4A7F7371BB2F3E4696B9E2F3FAA3BEF702BBE4BAC6B5EC5DB96CD4C22FC",
        "555C91315CBFB3C1F4E74C0814BF3C7D1A41F17D611749EBECDB30D733933E37",
        "5C79F0178A684309112AE9D5A90E8BF60449EFAD95E688BE0499B2CD6DBA1750",
        "659742EB3822673231678D6E2E4E9E0B447EE30F8AFE314708817A2925E030F4",
        "6B303AE4A7D595285432774E975D4D72DA7D90E84B82DD3BAC44A2A34EC3F9CC",
        "7119719283D1A03ABEAC31E10DE248986CAEC22A1D1D44C324FB61657903EAF2",
        "71A8B522C1A346E037AE8455DD68C4407CCDF48D973221830601A41C208EBF72",
        "766DEBA1F5EA81E02C207E289417CBD31AE47F40549059B599917EC37C2A467D",
        "88F7D3A6E924177AD51320AFA018783B8DACB0456D3AB47BDDD724422786E7E4",
        "890F09EB698E6E5F35F8A7A55069F7D21E7AD78DC93E3939C2C08C7EB806E6DD",
        "895E9E0A3D39C0F079EF75F929A5D5ABDEFB3DEE0102447B29D402611C2731CB",
        "8DCA47F911EB3A2EB9D57C6154704D2FD95597ED24B497271D057024D74A6601",
        "8DE9135E9E01AC30B12C9DE15B77B5D217570D564F0E0979E51FFB7A3B802419",
        "9293A83886A02096C5028B148C24F14F7D035D97C9BAFA243B43D800A1E96F39",
        "9F6C09B92CE760B8BCDCBE828948D2E982450612DFBF8860620EC94BFE8559A9",
        "A1406362CB7555E3B08D5EF3CC454A90D9EEFEC5A220E6C7772B592B5292E62E",
        "A40CCFA40A7A7C4F936D3C07ED942856DDBE35FD9441DAF5EB078260B325D192",
        "AE05230C05A5F9505E2354ADAF1E21B99ED9E573738B4A736EBEA1EB61C1B5DD",
        "AF05711EC77E66A21E9B4BF543618A7EDD271505C467CFA9B794B23A887053F3",
        "BCB6D41FF7DD1C72B60DDF193296A995525A27F1DEFCC5E93EA3F37FA6D457B6",
        "BFD4A73E1C2465E7E7167B531D5678C80135C0E3D33174E360CF28BCE36B3B8A",
        "D84AA31A2A2CC41AF5BA7A138E0F3D018E5320EF1BF5FFEB28E3AC7D0D705614",
        "D9B926852285F9381CA9B9514299599E72ABA4F80131D155EBD07A84BC29E189",
        "DE3FEE93FF8DDFD82ACBE76AF951F61BB029C7CDFED04113AC6A5684F1D9A633",
        "DE7016BB5FBA2C275D526FDF085992106C7B8F1FA0C3EEF5A3A08F059DCE8AED",
        "E9E03C9359B00E1A8FD33A4B09572AB4AE5B462699A24484F18E07A3056CE157",
        "EDCCE75AD5D4494A870D074C5B61D7D7D151E568CD75C2105D7AD800E98664CC",
        "EDFED6773196C78147C8F3981AD427C287F22DAC4C2678E957C2250FA76995F7",
        "F5A31880983FF7A84FDD559A607A480E00CD0D5E075B82F39546D21FF230F1E1",
        "F735D594860126D9A7FBD1BB7DAC9E5964CCD1B108F5BA9D5BED0E206F630656",
        "FB51246AE72061EBC4EEC02A8937BAD681879758E6A98FAE45B6E1F4781C9250",
        "FCF8F402F6E666B0D9BD6288DA64EB2C42E75051BEF723378FFEBE2CEC03F49D"
      ]
    },
    "ledger_hash": "B7D02C71869B280992E1F7868512ECDAA0325C968DC9BC8DC0924067CDB76BF7",
    "ledger_index": 68083439,
    "validated": true
  },
  "type": "response"
}
```
As you can see it can be fairly straightfoward working with the Ripple Library.
### Landscape
---
Ripple is in the Blockchain and Cryptocurrencies Financial Industry Domain, specifically utilizing blockchain as a payment protocol for remittances largely aimed at innovating the banking sector. Over the last 5-10 years blockchain and cryptocurrency has disrupted the remittance and payment sector on a global scale, even surpassing the valuation of traditional legacy companies such as VISA and Mastercard. Although Bitcoin was the first, Ripple has emerged as an early contender for implementing blockchain within banks. 
The most direct competitor to Ripple would be Stellar Lumen. In their early days, Stellar and Ripple were a lot alike because Jed McCaleb helped found both cryptocurrencies. Today, however, there are marked differences, even though Stellar occupies a similar niche in targeting financial services, as does Ripple.

Both Stellar and Ripple bring exceptionally fast and inexpensive transaction processing to the table. Ripple's transactions cost just a fraction of a penny and can be settled within seconds, while Stellar claims an average settlement time of two to five seconds, with 100,000 transactions costing just $0.01. Comparably, transactions on Ethereum's blockchain take longer and cost much more. The Stellar Development Foundation is also run as a nonprofit that aims to resolve the lack of access people all around the globe have to banking. In addition to securing digital identities, blockchain technology offers the ability for the underbanked population to exchange virtual currency without traditional bank accounts. Comparably, Ripple is a for-profit organization that's primarily focused on securing deals with large financial institutions. That's not to say Stellar isn't focusing on what it can do for big businesses, so much as to point out the variances between their nonprofit and for-profit approaches.

![Comparison](https://blockgeeks.com/wp-content/uploads/2019/06/Screen-Shot-2019-06-19-at-12.45.21-PM-1024x502.png.webp)
>A chart comparing Ripple and Stellar

Where Stellar could really stand out and give Ripple a run for its money (pun intended) is in regard to its decentralization. Though it's somewhat argumentative, Ripple's network is considered to be far more centralized than Stellar, even though the Stellar Development Foundation also controls a majority of Lumens. As noted by the website Invest in Blockchain, Ripple faced backlash in 2015 when founder McCaleb left the company and his funds were frozen. This drew attention to the fact that Ripple's controlling members could put the kibosh on anything they didn't like, which is the opposite of the decentralization that's at the heart of crypto use. Stellar hasn't faced nearly the same backlash from the crypto community. 
### Results
---
![Sentiment](https://s3.cointelegraph.com/uploads/2021-01/21a593b0-0bd3-4354-9060-2efb3e78ca22.jpg)
>Sentiment analysis comparing Ripple and Stellar performance

Ripple has had good results, striking deals within the idustry with it's first big break in mid-November 2017 when it was announced that it had partnered with American Express and Banco Santander in a real-world cross-border payment test. Under the terms of this test, American Express users making non-card payments with AmEx FX International to U.K. Santander accounts will have those payments processed over Ripple's blockchain and settled almost instantly. Ripple, which focuses solely on financial institutions, has suggested that its average processing time is around four seconds. Compared to the wait of up to five business days that can occur under the current banking system, Ripple offers financial institutions a game-changing solution with its blockchain.

Similarly, its token is proving useful in luring potential enterprise customers. In January, Ripple announced a partnership with money-transfer service MoneyGram International that would test its XRP token within the xRapid platform, which helps financial institutions that have on-demand remittance needs. 

Stellar's biggest break came in October when IBM announced that it had partnered with Stellar and KlickEx in the South Pacific region to expedite payment processing in the cross-border setting. Using IBM's blockchain and Stellar's Lumens token (XLM), IBM aimed to speed up validation and settlement times at 12 regional banks. While we've witnessed numerous blockchain partnerships in the financial services space, we've seen very few willing to use the native cryptocurrencies, as IBM chose to do with Stellar's Lumens. 
### Recommendations
---
If I were to advise the company, I would advise them to offer a more decentralized option for their payment product which would be more trusted by the community of cryptocurrency enthusiasts. XRP's lack of decentralization is it's biggest detriment to adoption among anybody who is in crypto for it's ideology and not just the money to be made with speculation. This would be beneficial because it would be more secure, since an immutable and decentralized currency is the only one which is fully trustable and unable to be manipulated. This change would require the use of more traditional blockchain that utilizes either proof-of-work, proof-of-stake, or a similar consensus method to process transactions instead of the centralized method which Ripple currently uses. These protocols are appropriate as a preffered consensus solution because they have been thoroughly tested and implemented many times before in other coins.

### Citations:
---

Contributors: John Leelike
