# Psicoin
psicoin open source code
Phouesaycoin (Pseudo Currency or PSI) is committed to the development of a third blockchain ecosystem beyond Bitcoin and Ethereum to achieve peer-to-peer value transfer through the Value Transfer Protocol ("Value Transfer Protocol"). In accordance with this agreement, a decentralized application development platform (“DApp Platform”) supporting multiple industries (including finance, the Internet of Things, supply chain, social networking, games, etc.) is built. Due to technological innovations, improved governance structures, and a wide range of applications, Purcell will become a public chain superior to Bitcoin and Ethereum:
From a technical point of view, Psyche has a strong development team that has achieved the first IPoS-based IPOs by introducing the Identity, Oracle, and Data feeds mechanisms and is compatible with the UTXO transaction model of the Bitcoin Improvement Proposals. (Incentives to prove equity) consensus mechanism smart contract platform. In terms of compliance, it also meets the regulatory requirements of different industries.
From the point of view of governance, Pseudocoin set up the Poseidon Foundation and committed itself to the development and construction of Pou Sai, the promotion of governance transparency and promotion, and promoted the safety and harmony of the open-source ecological society. Through the establishment of a good foundation governance structure, it helps manage the general and privileged issues of open source community projects from multiple dimensions including code management, financial management, and public relations, thereby ensuring the sustainability of quantum links and the effective management of internal funds. Sex and the safety of raised funds.
Analyzed from the perspective of the application of PUSCAN, Purcell has introduced the chain factors through “decentralized application” and “host control contract” to form a blockchain master contract that meets the real world business logic, supporting multiple industries and multiple Channels, eventually achieving Go Mobile. In the Psyche coin ecosystem, we will work with third-party developers to support the provision of mobile services from the technical infrastructure, including mobile wallets, mobile DApp applications, and mobile smart contract services. We also encourage third-party developers to join us in the development of blockchain mobile services to jointly promote the implementation of blockchain technology. As the most promising block chain ecosystem, Psyche currency perfectly combines the advantages of Bitcoin and Ethereum and solves the inherent defects of the existing block chain system. Purseco will continue to build the basic platform, develop and iterate various product development and commercialization projects, gradually form a blockchain economy, enhance industry efficiency, and promote efficient collaborative development of society. As a currency, it defines the blockchain economy.
Based on the classic Classic Proof of Stake as a consensus mechanism, the PurseCoin differs from Bitcoin and Ethereum's proof-of-work mechanism and is the first smart contract platform under the POS mechanism for the entire blockchain industry. It is also the first smart contract platform to support bitcoin ecology through EVM.
Recently, the PSI currency team released the development summary and development progress, and completed the first POS smart contract platform based on the Bitcoin UTXO model. It also became the second full support for Turing-complete smart contracts in addition to Ethereum. Blockchain platform. Want to implement in the account abstraction layer based on the UTXO model of Bitcoin, is it more complicated and more difficult than you think? This article elaborates on what PSI has done for reference and modification and has achieved much.
Note: Some of the content of this article comes from the PSI Technical White Paper
The Ethereum Virtual Machine (EVM) uses 256-bit machine code and is a stack-based virtual machine used to execute Ethereum smart contracts. Since EVM is designed for the Ethereum architecture, the Ethereum Account Model is used for value transmission. The design of the Epson is based on the Bitcoin UTXO model, so the Account Abstraction Layer is added to the model of the Pursecoin model to transform the UTXO model into an account model that can be executed by the EVM. In addition, PSI has also joined the Blockchain Interface so that the EVM can directly read the information on the currency.
1.EVM integration
By expanding the scripting language of the bitcoin network, three new operators have been added to the development of Psyche:
1. OP_EXEC - script code used to perform EVM transfer, and can trigger a special process in the transaction (more on this later);
2. OP_EXEC_ASSIGN – used to pass the relevant data (CALLERDATA in the EVM) and the address information needed to call the smart contract and execute the contents of the code in the contract. This operator can also send funds for smart contracts. Similar to OP_EXEC, special processes can also be triggered;
3. OP_TXHASH – pushes the current contract's ID hash into the stack, and can also recalculate the exception data in the account abstraction layer.

Figure 1: Model of transaction transmission architecture for PSI system
In the Bitcoin system, the corresponding transaction output can only be consumed after the verification script (ScriptSig) and the verification script (ScriptPubKey) are verified. For example, the lock script usually locks the output of a transaction to a bitcoin address (the hash value of the public key). The execution of the composite script will show the result only if the unlock script matches the conditions set in the lock script. True (the system returns a value of 1) so that the corresponding transaction output will be spent.
In the PSI system, we place more emphasis on the timeliness of smart contract execution. So we added the OP_EXEC and OP_EXEC_ASSIGN operators to the lock script. When the PSI system detects this operator, the entire network node will execute the transaction. In this way, the Bitcoin script plays a more important role in delivering relevant data to EVM than as a coding language. As with Ethereum executing smart contracts, contracts triggered by the OP_EXEC and OP_EXEC_ASSIGN operators change their state in their respective state databases.
