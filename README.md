# Blockchain Technology and Applications — Lecture 1 Notes

Professor Sandeep Shukla, IIT Kanpur

The lecture introduces blockchain technology, explains why tamper-resistant record-keeping is important, discusses real-world applications, and identifies the limitations of cryptocurrencies such as Bitcoin. Below are organized study notes based on your transcript.

## 1. What is blockchain?

A blockchain is a distributed, replicated data structure that uses cryptographic linking and consensus to maintain the integrity of records.

A traditional linked list connects nodes using memory addresses. A blockchain connects blocks using cryptographic hashes.

Complete Guide on Getting Started with Blockchain Technology -

[analyticsvidhya.com](<https://www.analyticsvidhya.com/blog/2022/10/complete-guide-on-getting-started-with-blockchain-technology/?utm_source=chatgpt.com>)

### Key characteristics

- Distributed: Multiple computers, called nodes, participate in maintaining the data.
- Replicated: Copies of the ledger are maintained across multiple nodes.
- Cryptographically linked: Each block refers to a previous block through a cryptographic hash.
- Consensus-based: Participating nodes follow a protocol to agree on which records are accepted.
- Tamper-resistant: Changing historical records is designed to be computationally difficult or detectable.
- Authenticated: Digital signatures can help verify who authorized a transaction.

### Important terminology

| Term | Meaning |
| --- | --- |
| Block | A collection of data or transactions |
| Hash | A fixed-length digest calculated from input data |
| Ledger | A record of transactions or events |
| Consensus | A process for agreeing on accepted records |
| Replication | Maintaining copies of data across multiple nodes |
| Data integrity | Assurance that data has not been improperly altered |
| Immutability | Resistance to changing records after they are accepted |
| Digital signature | A cryptographic mechanism for verifying authorization and authenticity |

Important: Blockchain is not absolutely impossible to tamper with. Its security depends on the protocol, cryptographic mechanisms, consensus assumptions, and the resources available to an attacker.

## 2. Why do we need blockchain?

The main motivation is to maintain trustworthy records without relying entirely on one central authority.

The professor presents several examples.

Checking Online Bank Account Balance

1. Banking transactions

Banks maintain transaction ledgers. An insider, compromised system, or fraudulent process could alter records or create unauthorized transactions. Tamper-resistant records can help detect unauthorized changes and improve auditability.

IoT To Improve The Efficiency Of Perishable Goods Transportation

2. Supply-chain provenance

Suppose ice cream arrives melted at a restaurant. Was it stored at the wrong temperature in the factory or in the delivery truck? Authenticated, timestamped sensor records can help establish the history of the product.

The Registry Department of Kanpur found irregularities worth 25 billion in an Income Tax survey कानपुर ने सरकार को लगाया 500 करोड़ का चूना, आयकर सर्वे में 25 अरब की गड़बड़ी मिली, Uttar-pradesh Hindi News - Hindustan

3. Land records

Fraudulent changes to property ownership records can cause disputes. A tamper-resistant history of ownership transfers and record modifications can improve traceability and accountability.

Cybersecurity identity verification system with biometric authentication password protection and secure access

4. Aadhaar e-KYC access logs

Users need confidence that records of access to their identity information are complete. If an administrator can secretly delete access logs, users cannot independently verify the history.

Faculty and Staff Registrar Information | Yeshiva University

5. University grade management

If an insider changes a student's grade after submission and removes the corresponding logs, the professor and student may have difficulty proving what happened. Auditable records can help detect such modifications.

### The common problem

All five applications involve a similar concern:

1. Someone creates or modifies a record.
2. A central authority or administrator maintains the database.
3. The administrator or an attacker may alter the record or delete its history.
4. Other participants may lack independent evidence of the original record.

Blockchain can provide a shared, tamper-resistant record of events, reducing reliance on a single party for record integrity.

However, blockchain does not automatically prove that the original information was truthful. For example, a sensor can report a false temperature, and blockchain can permanently preserve that false report.

## 3. Traditional systems versus blockchain

| Feature | Traditional centralized database | Blockchain |
| --- | --- | --- |
| Record management | Usually controlled by a central organization | Shared across participating nodes |
| Trust | Relies heavily on the database operator and controls | Relies on protocol rules, cryptography, and consensus |
| Record modification | Authorized administrators may update records | Historical changes may be restricted or detectable |
| Auditability | Depends on logging and access controls | Can provide a shared, verifiable transaction history |
| Performance | Often efficient for ordinary transactions | May incur consensus and replication overhead |
| Best use case | Systems with a trusted operator | Systems needing shared records among parties with limited mutual trust |

Blockchain is not automatically superior. If all participants trust one organization and a conventional database meets their needs, a blockchain may add unnecessary complexity.

## 4. Why is cryptocurrency not the main focus?

Bitcoin introduced an influential practical application of blockchain. Ethereum subsequently popularized programmable blockchain applications and smart contracts.

Nevertheless, the professor emphasizes that blockchain is much broader than cryptocurrency.

### Major cryptocurrency concerns

- Illegal activities: Some criminals have used cryptocurrencies for illicit transactions and ransomware payments.
- Price volatility: Cryptocurrency prices can fluctuate substantially.
- Energy consumption: Bitcoin's proof-of-work mining can consume substantial electricity.
- Mining concentration: Large mining operators may control a disproportionate share of computational power.
- Private-key loss or theft: Anyone who obtains the necessary private key may be able to spend the associated funds.
- Exchange failures: Users may lose funds if an exchange is hacked, mismanaged, or unable to provide access to assets.
- Smart-contract vulnerabilities: Programming errors can lead to unauthorized transfers or financial losses.
- Regulatory uncertainty: Laws and restrictions differ across jurisdictions.

The professor's central message is that the underlying technology is worth studying independently of cryptocurrency investment.

## 5. Bitcoin and the double-spending problem

One of the most important technical concepts introduced in the lecture is double spending.

A digital file can be copied easily. If digital money were simply a file, someone could copy it and attempt to spend the same money twice.

### Example: One digital coin, two payments

Alice owns one digital coin

Payment A

Alice pays Bob

Payment B

Alice pays Carol

Problem: Both payments attempt to spend the same coin.

### How is double spending prevented?

The lecture introduces a transaction-history approach.

1. Each transaction identifies the coins or previous outputs it spends.
2. The system checks whether the inputs are valid and have not already been spent.
3. The transaction must be authorized by the appropriate owners.
4. The total value of the inputs must equal the total value of the outputs, accounting for any permitted transaction fees.
5. The network uses its transaction-validation and consensus rules to determine which transactions are accepted.

The key question becomes: Who maintains the history and decides which transaction is valid?

A traditional solution is a trusted third party, such as a central payment operator. Blockchain aims to solve this through distributed consensus, allowing participants to maintain a shared transaction history without relying entirely on a single record-keeper.

## 6. What is a 51% attack?

In a proof-of-work blockchain such as Bitcoin, miners compete to perform computational work.

If an attacker controls a majority of the network's active mining hash power, the attacker may be able to reorganize recent transaction history and reverse their own payments, subject to the protocol and network conditions.

This is commonly called a 51% attack.

It does not mean an attacker can arbitrarily forge other users' digital signatures or spend their coins without the required keys. However, majority control can seriously undermine transaction finality and trust in the ledger.

## 7. How does a blockchain support digital coins?

The professor introduces a simplified digital-coin model based on public-key cryptography.

How are Bitcoins traded and what is a wallet signature?

[coincover.com](<https://www.coincover.com/blog/how-are-bitcoins-traded-and-what-is-a-wallet-signature?utm_source=chatgpt.com>)

The basic process is:

1. A coin is created and associated with a transaction record.
2. The owner authorizes a transfer using a digital signature.
3. The transfer identifies the recipient, commonly through an address derived from public-key information.
4. The transaction links to the earlier transaction history establishing the source of the funds.
5. The network validates the transaction and determines whether it can be included in the ledger.

The transaction history helps participants verify where the funds came from and whether they have already been spent.

In modern Bitcoin, this is implemented using transaction inputs and outputs rather than simply transferring a single coin object between people.

## 8. Supply-chain integrity: Why cryptography alone is insufficient

The ice-cream example reveals a more subtle problem.

Suppose a factory, a delivery company, and a restaurant all participate in a supply chain. They use temperature sensors to record storage conditions.

### Potential attacks

| Attack | Explanation | Possible protection |
| --- | --- | --- |
| Man-in-the-middle | An attacker intercepts and alters sensor messages | Message authentication and digital signatures |
| Replay attack | An attacker resends old sensor readings | Timestamps, sequence numbers, and freshness checks |
| Impersonation | One supplier pretends to be another | Device authentication and digital certificates |
| Data repudiation | A supplier denies having sent a record | Properly managed digital signatures and audit trails |
| Centralized data tampering | A central collector modifies or deletes records | Independent verification and tamper-resistant shared records |

The lecture points out that cryptography can protect messages in transit, but it does not fully solve the problem of multiple organizations needing to share and verify records.

A central cloud provider could collect everything, but then participants must trust that provider.

Blockchain can help by distributing record validation and maintenance across participants according to agreed rules.

Limitation: Blockchain cannot guarantee that a physical sensor is accurate, that a supplier entered truthful data, or that a compromised device has not generated fraudulent readings. Trusted hardware, inspections, and other real-world controls may still be necessary.

## 9. What is trusted computing?

Trusted computing refers to having confidence that a computing system processes, stores, and transmits information correctly and securely.

The lecture identifies several potential sources of compromise:

- Hardware vulnerabilities and side-channel attacks.
- Operating-system or firmware weaknesses.
- Memory and cache information leakage.
- Hypervisor vulnerabilities in virtualized environments.
- Application bugs and cyberattacks.
- Malicious or dishonest system administrators.
- Unauthorized changes to databases and system logs.

This leads to two important questions:

- Trust model: Which entities or components are assumed to behave correctly?
- Threat model: Which attackers, failures, and malicious actions must the system withstand?

A blockchain can strengthen the integrity and auditability of records, but it does not automatically make the entire computing environment trustworthy.

## 10. Types of blockchain introduced

The lecture previews different blockchain designs based on who is permitted to participate and how much the participants trust one another.

| Type | General meaning |
| --- | --- |
| Public, permissionless | Anyone can generally join the network and participate under its protocol rules |
| Permissioned | Participation or validation rights are restricted to authorized entities |
| Private blockchain | A blockchain operated within a restricted organization or group |

Terminology can overlap: a private blockchain is often permissioned. The exact distinction depends on who may read records, submit transactions, validate blocks, and administer the network.

The correct choice depends on the application's trust assumptions, governance requirements, privacy needs, and performance requirements.

## 11. The most important lessons from Lecture 1

- Blockchain is a distributed record-keeping technology, not just a cryptocurrency platform.
- Data integrity is one of its main objectives.
- Hashes link records cryptographically, while digital signatures authenticate transactions.
- Consensus helps participating nodes agree on accepted records.
- Replication helps maintain availability and shared copies of the ledger.
- Double spending is a fundamental problem in digital currency systems.
- Supply-chain tracking, land records, banking, identity-access logs, and academic records are potential blockchain applications.
- Blockchain can reduce dependence on a single trusted record-keeper, but it does not eliminate every form of trust.
- Blockchain is not always necessary; a conventional database may be a better solution.
- The trust model and threat model should be understood before selecting a blockchain architecture.

## Quick revision quiz

## Test your understanding

0 of 5

1. What is the primary objective of blockchain emphasized in the lecture?

Increasing internet speed

Maintaining data integrity

Replacing all databases

Eliminating cryptography

2. What is double spending?

Paying two transaction fees

Copying a private key

Spending the same digital funds more than once

Creating two public keys

3. What does a cryptographic hash primarily provide in blockchain linking?

A link based on a digest of data

A guarantee that the original data is truthful

Automatic identity verification

Unlimited storage

4. Why might a blockchain be useful in a supply chain?

It guarantees every sensor is correct

It removes the need for all inspections

It supports shared, tamper-resistant records among multiple parties

It prevents all delivery delays

5. When might a traditional database be preferable?

When one trusted operator can meet the requirements efficiently

Whenever data must be stored

When cryptography is prohibited

Whenever multiple records exist

 Reset quiz

Recommended next step: Study the fundamentals of cryptography—hash functions, public and private keys, digital signatures, and message authentication codes—because these concepts underpin the blockchain mechanisms introduced in this lecture.
