# Awesome Blockchain

[![Awesome](https://awesome.re/badge.svg)](https://github.com/yjjnls/awesome-blockchain)

> Curated list of resources for the development and applications of block chain.

The blockchain is an incorruptible digital ledger of economic transactions that can be programmed to record not just financial transactions but virtually everything of value (by [Don Tapscott](https://www.linkedin.com/pulse/whats-next-generation-internet-surprise-its-all-don-tapscott)).

<font color=#0099ff size=3>**This is not a simple collection of Internet resources, but verified and organized data ensuring it's really suitable for your learning process and useful for your development and application.**</font> 

## Contents

- [Awesome Blockchain](#awesome-blockchain)
    - [Contents](#contents)
    - [Frequently Asked Questions (F.A.Q.s) & Answers](#frequently-asked-questions-faqs--answers)
    - [Basic Introduction](#basic-introduction)
        - [Encryption knowledge](#encryption-knowledge)
    - [Development Tutorial](#development-tutorial)
        - [BitCoin](#bitcoin)
        - [Ethereum](#ethereum)
        - [Consortium Blockchain](#consortium-blockchain)
            - [Fabric](#fabric)
            - [FISCO-BCOS](#fisco-bcos)
    - [Releated Tools](#releated-tools)
        - [Solidity](#solidity)
        - [truffle](#truffle)
        - [web3.js](#web3js)
    - [Projects and Applications](#projects-and-applications)
        - [Monero](#monero)
        - [IOTA](#iota)
        - [EOS](#eos)
        - [IFPS](#ifps)
    - [Further Extension](#further-extension)
        - [Books](#books)
        - [Applications](#applications)
            - [Identity Applications](#identity-applications)
                - [Public Blockchain Identity](#public-blockchain-identity)
                - [Blockchain as a collateral](#blockchain-as-a-collateral)
                - [Unclear](#unclear)
                - [Guidance](#guidance)
            - [Internet of Things Applications](#internet-of-things-applications)
            - [Energy Applications](#energy-applications)
            - [Media and Journalism](#media-and-journalism)
    - [Contribute](#contribute)

## Frequently Asked Questions (F.A.Q.s) & Answers

**Q: What's a Blockchain?**

A: A blockchain is a distributed database with a list (that is, chain) of records (that is, blocks) linked and secured by
digital fingerprints (that is, crypto hashes).
Example from [`blockchain.rb`](https://github.com/openblockchains/awesome-blockchains/blob/master/blockchain.rb/blockchain.rb):

```ruby
[#<Block:0x1eed2a0
    @timestamp     = 1637-09-15 20:52:38,
    @data          = "Genesis",
    @previous_hash = "0000000000000000000000000000000000000000000000000000000000000000",
    @hash          = "edbd4e11e69bc399a9ccd8faaea44fb27410fe8e3023bb9462450a0a9c4caa1b">,
    #<Block:0x1eec9a0
    @timestamp     = 1637-09-15 21:02:38,
    @data          = "Transaction Data...",
    @previous_hash = "edbd4e11e69bc399a9ccd8faaea44fb27410fe8e3023bb9462450a0a9c4caa1b",
    @hash          = "eb8ecbf6d5870763ae246e37539d82e37052cb32f88bb8c59971f9978e437743">,
    #<Block:0x1eec838
    @timestamp     = 1637-09-15 21:12:38,
    @data          = "Transaction Data......",
    @previous_hash = "eb8ecbf6d5870763ae246e37539d82e37052cb32f88bb8c59971f9978e437743",
    @hash          = "be50017ee4bbcb33844b3dc2b7c4e476d46569b5df5762d14ceba9355f0a85f4">,
    ...
```

![](Basic/img/blockchain-jesus.png)

**Q: What's a Hash? What's a (One-Way) Crypto(graphic) Hash Digest Checksum**?

A: A hash e.g. `eb8ecbf6d5870763ae246e37539d82e37052cb32f88bb8c59971f9978e437743`
is a small digest checksum calculated
with a one-way crypto(graphic) hash digest checksum function
e.g. SHA256 (Secure Hash Algorithm 256 Bits)
from the data. Example from [`blockchain.rb`](blockchain.rb/blockchain.rb):

```ruby
def calc_hash
  sha = Digest::SHA256.new
  sha.update( @timestamp.to_s + @previous_hash + @data )
  sha.hexdigest   ## returns "eb8ecbf6d5870763ae246e37539d82e37052cb32f88bb8c59971f9978e437743"
end
```

A blockchain uses

-   the block timestamp (e.g. `1637-09-15 20:52:38`) and
-   the hash from the previous block (e.g. `edbd4e11e69bc399a9ccd8faaea44fb27410fe8e3023bb9462450a0a9c4caa1b`) and finally
-   the block data (e.g. `Transaction Data...`)

to calculate the new hash digest checksum, that is, the hash
e.g. `be50017ee4bbcb33844b3dc2b7c4e476d46569b5df5762d14ceba9355f0a85f4`.

**Q: What's a Merkle Tree?**

A: A Merkle tree is a hash tree named after Ralph Merkle who patented the concept in 1979
(the patent expired in 2002). A hash tree is a generalization of hash lists or hash chains where every leaf node (in the tree) is labelled with a data block and every non-leaf node (in the tree)
is labelled with the crypto(graphic) hash of the labels of its child nodes. For more see the [Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree) Wikipedia Article.

Note: By adding crypto(graphic) hash functions you can "merkelize" any data structure.

**Q: What's a Merkelized DAG (Directed Acyclic Graph)?**

A: It's a blockchain secured by crypto(graphic) hashes that uses a directed acyclic graph data structure (instead of linear "classic" linked list).

Note: Git uses merkelized dag (directed acyclic graph)s for its blockchains.

**Q: Is the Git Repo a Blockchain?**

A: Yes, every branch in the git repo is a blockchain.
The "classic" Satoshi-blockchain is like a git repo with a single master branch (only).

## Basic Introduction

<!--    
### Encryption knowledge
   -->

-   **Encryption knowledge**  
    * [Asymmetric encryption](./Basic/crypto.md#%E9%9D%9E%E5%AF%B9%E7%A7%B0%E5%8A%A0%E5%AF%86)  
    * [Digital signature & certificate](./Basic/crypto.md#%E6%95%B0%E5%AD%97%E7%AD%BE%E5%90%8D)  
    * [Merkle tree](./Basic/crypto.md#merkle-tree)  
    * [Merkle tree in blockchain](./Basic/merkle_tree_in_blockchain.md)  
    * [Merkle DAG](http://www.sohu.com/a/247540268_100222281)   
    <!--   
    ### Consensus
       -->
-   **Consensus**  
    <!--    
    ### Account and transaction model
       -->
-   **Account and transaction model**  
    <!-- 
    ### Exchange
        -->
-   **Exchange**  
    <!-- 
    ### Applications
        -->
-   **Applications**  
    * [Do You Need a Blockchain?](https://spectrum.ieee.org/computing/networks/do-you-need-a-blockchain)  
    * [What can't blockchain do?](https://www.jianshu.com/p/70f6a29a6296)  
    * [More](./Extension/application.md) 
    <!--     
    ### Capacity expansion and chain governance
        -->
-   **[Capacity expansion and chain governance](https://github.com/yfeng125/blockchain-tutorial/blob/master/doc/%E2%80%8B25.%E6%AF%94%E7%89%B9%E5%B8%81%EF%BC%9A%E6%89%A9%E5%AE%B9%E4%B9%8B%E4%BA%89%E3%80%81IFO%E4%B8%8E%E9%93%BE%E4%B8%8A%E6%B2%BB%E7%90%86.md)**   
    <!--     
    ### Digital currency ranking
        -->
-   **[Digital currency ranking](https://coinmarketcap.com/)**   

<!-- -   [ ] [Consensus](<>)  
-   [Account and transaction model](./Basic/account.md)  
-   [ ] [Bitcoin basics](<>)  
-   [ ] [Ethereum basics](<>)  
    - [ ] []()链上治理
-   [ ] [Exchange](<>)  
-   [Applications](./Extension/application.md)  -->

## Development Tutorial

### [BitCoin](https://github.com/bitcoin/bitcoin)

[<img src="https://bitcoin.org/img/icons/logotop.svg" align="right" width="120">](https://bitcoin.org/zh_CN/)

-   [BitCoin white paper](https://bitcoin.org/bitcoin.pdf) / [Chinese version](BitCoin/white%20paper.md)
-   [Mastering BitCoin](https://github.com/bitcoinbook/bitcoinbook) / [Chinese version](http://book.8btc.com/books/6/masterbitcoin2cn/_book/) / [pdf download](http://book.8btc.com/master_bitcoin?export=pdf)
-   [More](./BitCoin/awesome.md)

### Ethereum

[<img src="https://github.com/yjjnls/Notes/blob/master/img/ethereum.png" align="right" width="80">](https://www.hyperledger.org/projects/fabric)

-   [Ethereum white paper](https://github.com/ethereum/wiki/wiki/White-Paper) / [以太坊白皮书](./Ethereum/white%20paper.md)
-   [Ethereum wiki](https://github.com/ethereum/wiki/wiki)
-   [Ethereum problems](https://github.com/ethereum/wiki/wiki/Problems)

### Consortium Blockchain
-   [The Byzantine Generals Problem](https://people.eecs.berkeley.edu/~luca/cs174/byzantine.pdf)
-   [Is consortium blockchain better?](http://www.infoq.com/cn/news/2018/10/is-consortium-blockchain-better)   
-   [5 consortium blockchain comparison](http://www.infoq.com/cn/articles/5-consortium-blockchain-comparison) / [quick version](https://upload-images.jianshu.io/upload_images/11336404-f753396df0e930c8.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)    
-   [FISCO BCOS vs Fabric](http://www.infoq.com/cn/news/2018/09/uncover-consortium-blockchain)   

*   **Implement a consortium blockchain using ethereum**  
-   [Building a Private Ethereum Consortium](https://www.microsoft.com/developerblog/2018/06/01/creating-private-ethereum-consortium-kubernetes/)
-   [Deploying a private Ethereum blockchain to Microsoft Azure Cloud](https://www.youtube.com/watch?v=HsConsFaZG8)
-   [Ethereum Consortium Network Deployments Made Easy](https://github.com/CatalystCode/ibera-ethereum-consortium-blockchain-network)
-   [How to Set Up a Private Ethereum Blockchain in 20 Minutes](https://arctouch.com/blog/how-to-set-up-ethereum-blockchain/)


#### Fabric

[<img src="https://www.hyperledger.org/wp-content/uploads/2018/03/Hyperledger_Fabric_Logo_Color.png" align="right" width="120">](https://www.hyperledger.org/projects/fabric)

#### [FISCO-BCOS](https://github.com/FISCO-BCOS/Wiki)

## Releated Tools

### Solidity

### truffle

### web3.js

## Projects and Applications

### Monero

[<img src="https://avatars0.githubusercontent.com/u/20126597?s=200&v=4" align="right" width="80">](https://github.com/iotaledger)  
### IOTA  

**Q: What is IOTA?**

**IOTA** is a revolutionary new transactional settlement and data integrity layer for the Internet of Things. It’s based on a new distributed ledger architecture, the **Tangle**, which overcomes the inefficiencies of current **Blockchain** designs and introduces a new way of reaching consensus in a **decentralized peer-to-peer system**. For the first time ever, through IOTA people can transfer money without any fees. This means that even infinitesimally small nanopayments can be made through IOTA.

**IOTA** is the missing puzzle piece for **the Machine Economy** to fully emerge and reach its desired potential. We envision IOTA to be the public, permissionless backbone for the Internet of Things that enables true interoperability between all devices.

-   [IOTA](https://iota.org) - Next Generation Blockchain
-   [Whitepaper](https://iota.org/IOTA_Whitepaper.pdf) - The Tangle
-   [Wikipedia](https://en.wikipedia.org/wiki/IOTA_(Distributed_Ledger_Technology))
-   [A Primer on IOTA](https://blog.iota.org/a-primer-on-iota-with-presentation-e0a6eb2cc621) - A Primer on IOTA (with Presentation)
-   [IOTA China](http://iotachina.com/) - IOTA China 首页
-   [IOTA Italia](http://iotaitalia.com/) - IOTA Italia
-   [IOTA Korea](http://blog.naver.com/iotakorea) - IOTA 한국
-   [IOTA Japan](http://lhj.hatenablog.jp/entry/iota) - IOTA 日本
-   [IOTA on Reddit](https://www.reddit.com/r/Iota/)


+   [**How to get started**](https://github.com/iotaledger/iri#how-to-get-started)   
+   [**More resouces**](./Extension/iota.md)  


### EOS

<!-- [<img src="https://avatars2.githubusercontent.com/u/10536621?s=200&v=4" align="right" width="40">](https://github.com/ipfs/ipfs) -->

### IFPS

## Further Extension

### Books

-   [区块链技术指南](https://yeasy.gitbooks.io/blockchain_guide/content/) by Baohua Yang, 2017
    <!-- -   [区块链原理、设计与应用](https://github.com/yjjnls/books/blob/master/block%20chain/%E5%8C%BA%E5%9D%97%E9%93%BE%E5%8E%9F%E7%90%86%E3%80%81%E8%AE%BE%E8%AE%A1%E4%B8%8E%E5%BA%94%E7%94%A8.pdf) -->
-   [**Blockchain: from Digital Currency to Credit Society**](https://github.com/yjjnls/books/blob/master/block%20chain/%E5%8C%BA%E5%9D%97%E9%93%BE%20%E4%BB%8E%E6%95%B0%E5%AD%97%E8%B4%A7%E5%B8%81%E5%88%B0%E4%BF%A1%E7%94%A8%E7%A4%BE%E4%BC%9A.pdf)
-   [**Attack of the 50 Foot Blockchain: Bitcoin, Blockchain, Ethereum & Smart Contracts**](https://davidgerard.co.uk/blockchain/table-of-contents/) by David Gerard, London, 2017 --
    _What is a bitcoin? ++
    The Bitcoin ideology ++
    The incredible promises of Bitcoin! ++
    Early Bitcoin: the rise to the first bubble ++
    How Bitcoin mining centralised ++
    Who is Satoshi Nakamoto? ++
    Spending bitcoins in 2017 ++
    Trading bitcoins in 2017: the second crypto bubble ++
    Altcoins ++
    Smart contracts, stupid humans ++
    Business bafflegab, but on the Blockchain ++
    Case study: Why you can’t put the music industry on a blockchain_

-   [**Mastering Bitcoin - Programming the Open Blockchain**](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch09.asciidoc) 2nd Edition,
    by Andreas M. Antonopoulos, 2017 - FREE (Online Source Version) --
    _What Is Bitcoin? ++
    How Bitcoin Works ++
    Bitcoin Core: The Reference Implementation ++
    Keys, Addresses ++
    Wallets ++
    Transactions ++
    Advanced Transactions and Scripting ++
    The Bitcoin Network ++
    The Blockchain ++
    Mining and Consensus ++
    Bitcoin Security ++
    Blockchain Applications_

-   [**Programming Blockchains in Ruby from Scratch Step-by-Step Starting w/ Crypto Hashes... ( Beta / Rough Draft )**](https://github.com/yukimotopress/programming-blockchains-step-by-step)
    by Gerald Bauer et al, 2018 - FREE (Online Version) --
    _(Crypto) Hash ++
    (Crypto) Block ++
    (Crypto) Block with Proof-of-Work ++
    Blockchain! Blockchain! Blockchain! ++
    Blockchain Broken? ++
    Timestamping ++
    Mining, Mining, Mining - What's Your Hash Rate? ++
    Bitcoin, Bitcoin, Bitcoin ++
    (Crypto) Block with Transactions (Tx)_


-   [**Programming Cryptocurrencies and Blockchains in Ruby ( Beta / Rough Draft )**](http://yukimotopress.github.io/blockchains)
    by Gerald Bauer et al, 2018 - FREE (Online Version) @ Yuki & Moto Press Bookshelf --
    _Digital $$$ Alchemy - What's a Blockchain? -
    How-To Turn Digital Bits Into $$$ or €€€? •
    Decentralize Payments. Decentralize Transactions. Decentralize Blockchains. •
    The Proof of the Pudding is ... The Bitcoin (BTC) Blockchain(s)
    \++
    Building Blockchains from Scratch -
    A Blockchain in Ruby in 20 Lines! A Blockchain is a Data Structure  •
    What about Proof-of-Work? What about Consensus?   •
    Find the Lucky Number - Nonce == Number Used Once
    \++
    Adding Transactions -
    The World's Worst Database - Bitcoin Blockchain Mining  •
    Tulips on the Blockchain! Adding Transactions
    \++
    Blockchain Lite -
    Basic Blocks  •
    Proof-of-Work Blocks  •
    Transactions
    \++
    Merkle Tree -
    Build Your Own Crypto Hash Trees; Grow Your Own Money on Trees  •
    What's a Merkle Tree?   •
    Transactions
    \++
    Central Bank -
    Run Your Own Federated Central Bank Nodes on the Blockchain Peer-to-Peer over HTTP  •
    Inside Mining - Printing Cryptos, Cryptos, Cryptos on the Blockchain
    \++
    Awesome Crypto
    \++
    Case Studies - Dutch Gulden  • Shilling  • CryptoKitties (and CryptoCopycats)_

-   [**Blockchain for Dummies, IBM Limited Edition**](https://www.ibm.com/blockchain/what-is-blockchain.html) by Manav Gupta, 2017 - FREE (Digital Download w/ Email) --
    _Grasping Blockchain Fundamentals ++
    Taking a Look at How Blockchain Works ++
    Propelling Business with Blockchains ++
    Blockchain in Action: Use Cases ++
    Hyperledger, a Linux Foundation Project ++
    Ten Steps to Your First Blockchain application_

-   [**Get Rich Quick "Business Blockchain" Bible - The Secrets of Free Easy Money**](https://github.com/bitsblocks/get-rich-quick-bible), 2018 - FREE --
    _Step 1: Sell hot air. How? ++
    Step 2: Pump up your tokens. How? ++
    Step 3: Revolutionize the World. How?_

-   [**Mastering Ethereum - Building Contract Services and Decentralized Apps on the Blockchain**](https://github.com/ethereumbook/ethereumbook) -
    by Andreas M. Antonopoulos, Gavin Wood, 2018 - FREE (Online Source Version)
    _What is Ethereum ++
    Introduction ++
    Ethereum Clients ++
    Ethereum Testnets ++
    Keys and Addresses ++
    Wallets	++
    Transactions ++
    Contract Services ++
    Tokens ++
    Oracles ++
    Accounting & Gas ++
    EVM (Ethereum Virtual Machine) ++ 	
    Consensus ++		
    DevP2P (Peer-To-Peer) Protocol ++
    Dev Tools and Frameworks ++
    Decentralized Apps ++
    Ethereum Standards (EIPs/ERCs)_

-   [**Building Decentralized Apps on the Ethereum Blockchain**](https://www.manning.com/books/building-ethereum-dapps) by Roberto Infante, 2018 - FREE chapter 1 --
    _Understanding decentralized applications ++
    The Ethereum blockchain ++
    Building contract services in (JavaScript-like) Solidity ++
    Running contract services on the Ethereum blockchain ++
    Developing Ethereum Decentralized apps with Truffle ++
    Best design and security practice_


-   [**Best of Bitcoin Maximalist - Scammers, Morons, Clowns, Shills & BagHODLers - Inside The New New Crypto Ponzi Economics**](https://github.com/bitsblocks/bitcoin-maximalist), 2018 - FREE 

-   [**Crypto Facts - Decentralize Payments - Efficient, Low Cost, Fair, Clean - True or False?**](https://github.com/bitsblocks/crypto-facts), 2018 - FREE 

-   [**IslandCoin White Paper - A Pen and Paper Cash System - How to Run a Blockchain on a Deserted Island**](https://github.com/bitsblocks/islandcoin-whitepaper)
    by Tal Kol -- 
    _Motivation ++
    Consensus ++
    Transaction and Block Specification -
    Transaction format •
    Block format •
    Genesis block ++
    References_

### Applications

#### Identity Applications

##### Public Blockchain Identity

-   [Blockstack](https://blockstack.org) - Platform for decentralized, server-less apps where users control their data. Identity included.
-   [Evernym](http://www.evernym.com) - Self-Sovereign identity built on top of open source permissioned blockchain.
-   [Jolocom](https://jolocom.com) - Self-sovereing identity wallet.
-   [SIN](https://en.bitcoin.it/wiki/Identity_protocol_v1) - Proposed identity protocol for BitCoin.
-   [uPort](https://www.uport.me) - Self-Sovereign identity on [Ethereum](https://ethereum.org) by [ConsenSys](https://consensys.net).

##### Blockchain as a collateral

-   [ShoCard](https://shocard.com) - Proprietary digital identity service, uses blockchain for time-stamping and secure documents exchange.
-   [Tradle](https://tradle.io/) - Makes a bank on blockchain, identity as a collateral.

##### Unclear

-   [KYC Chain](http://kyc-chain.com) - Secure platform for sharing verifiable identity claims, data or documents among financial institutions.
-   [ObjectChain Collab](http://www.objectchain-collab.com) - Cross-industry collaboration over distributed identity.
-   [UniquID](http://uniquid.com) - Identity both for people and devices.
-   [Vida Identity](https://vidaidentity.com) - Enterprise-grade Blockchain Identity Software.

##### Guidance

-   [ID3](https://idcubed.org) - Institute for Data Driven Design, explores issues around self-sovereign identity, and distributed organizations.
-   [OpenCreds](http://opencreds.org) - W3C Credentials Community Group.
-   [TAO Network Identity](http://tao.network/portfolio-item/the-identity-system/) - Description of blockchain identity by Tao.Network.

#### Internet of Things Applications

-   [Chronicled](http://www.chronicled.com) - IoT devices registry on blockchain.
-   [Filament](http://filament.com) - Software and hardware for decentralized Intranet of Things systems
-   [IOTA](http://www.iotatoken.com) - Decentralized Internet of Things token on blockless blockchain.
-   [Machinomy](http://machinomy.com) - Distributed platform for IoT micropayments.
-   [Project Oaken](https://www.projectoaken.com) - IoT blockchain platform.
-   [Slock.it](https://slock.it) - Ethereum-based platform for building Shared Things.

#### Energy Applications

-   [bankymoon](http://bankymoon.co.za/) - Blockchain consultancy. [Presented](http://goo.gl/L6vJBx) bitcoin-topped smart electricity meter. Once topped up, it chooses a plan, and starts moving energy.
-   [Co-Tricity](https://co-tricity.com/) - Decentralised energy marketplace by [Innogy](https://innovationhub.innogy.com/) and [ConsenSys](https://consensys.net).
-   [Electron](http://www.electron.org.uk/) - Reinventing energy on blockchain.
-   [GridSingularity](http://gridsingularity.com) - Blockchain for Smart Grid. Declare three years of work on the technology.
-   [lo3 energy](http://lo3energy.com) - Energy Services, Product Research & Development. Makers of [Brooklyn Microgrid](http://brooklynmicrogrid.com) along with [ConsenSys](https://consensys.net).
-   [lumo](https://lumoenergy.com.au) - Energy provider. Experiment with blockchain.
-   [PowerLedger](https://powerledger.io) - Decentralised energy marketpace.
-   [PowerPeers](https://www.powerpeers.nl/) - Peer-to-peer energy marketplace in the Netherlands.
-   [Solar Change](http://www.solarchange.co/) - Makers of [Solar Coin](http://solarcoin.org/). AltCoin for a MW of solar power.
-   [Terraledger](https://terraledger.com) - Provider of Renewable Energy Certificates.
-   [ImpactPPA](https://impactppa.com) - Reinvesting of power generated under Power Purchase Agreement in more PPAs.

#### Media and Journalism

-   [Steem](https://steem.io) - Decentralized social network which incentivises content creation and curation.
-   [PopChest](https://popchest.com) - Incentivized distributed video platform.
-   [Civil](https://joincivil.com) - Decentralized newsmaking platform. 

## Contribute

Contributions welcome! 

1.  Fork it (<https://github.com/yjjnls/awesome-blockchain/fork>)
2.  Clone it (`git clone https://github.com/yjjnls/awesome-blockchain`)
3.  Create your feature branch (`git checkout -b your_branch_name`)
4.  Commit your changes (`git commit -m 'Description of a commit'`)
5.  Push to the branch (`git push origin your_branch_name`)
6.  Create a new Pull Request

If you found this resource helpful, give it a 🌟 otherwise contribute to it and give it a ⭐️.
