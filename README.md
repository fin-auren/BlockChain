# Blockchain Technology and Applications 

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


## 1. Introduction to cryptography

Cryptography is the science of protecting information using mathematical techniques. In blockchain, it is primarily used to protect data integrity, verify transactions, establish identities, and secure communication.

### Basic terminology

Plaintext

The original, readable message before encryption.

Example: `Transfer 10 coins to Bob`

Encryption (Enciphering)

The process of converting plaintext into an unreadable form using an encryption algorithm and a key.

Ciphertext

The encrypted, unreadable version of the original message.

Decryption (Deciphering)

The process of recovering the original plaintext from ciphertext using the appropriate decryption key.

### Encryption and decryption equations

Let:

- $M$ = plaintext message
- $E$ = encryption function
- $D$ = decryption function
- $C$ = ciphertext

Encryption:

$$
C=E_K(M)
$$

Decryption:

$$
M=D_K(C)
$$

The essential requirement is:

$$
D_K(E_K(M))=M
$$

Here, $K$ represents the relevant key or keys.

## 2. Symmetric vs. asymmetric cryptography

These are the two major types of cryptographic systems discussed in the lecture.

Surviving a cyber security job interview (Cryptography) - JDriven Blog

A. Symmetric-key cryptography

The sender and receiver use the same secret key, or keys that can be efficiently derived from each other.

- Very fast and efficient.
- Suitable for encrypting large amounts of data.
- Main challenge: securely sharing and managing the secret key.

Examples: AES, DES, 3DES, Blowfish.

What's Asymmetric Encryption? - Babypips.com

B. Asymmetric-key cryptography

Uses a mathematically related pair of keys: a public key and a private key.

- The public key can be shared openly.
- The private key must remain secret.
- Generally slower than symmetric encryption.
- Supports public-key encryption, digital signatures, and key establishment, depending on the algorithm.

Examples: RSA, ElGamal, Diffie–Hellman for key agreement, and elliptic-curve cryptography.

### Comparison table

| Feature | Symmetric cryptography | Asymmetric cryptography |
| --- | --- | --- |
| Keys | Shared secret key | Public/private key pair |
| Speed | Generally fast | Generally slower |
| Key distribution | Difficult to secure | Can facilitate secure key establishment |
| Large data encryption | Very suitable | Usually not preferred |
| Digital signatures | Does not directly provide public-verifiable signatures | Supports digital signatures with suitable algorithms |
| Blockchain use | Efficient encryption where needed | Key establishment and transaction signatures |

### The key-management problem

If $n$ participants all need separate shared symmetric keys with every other participant, the number of keys required is:

$$
\frac{n(n-1)}{2}
$$

For example:

| Participants | Pairwise keys required |
| --- | --- |
| 2 | 1 |
| 3 | 3 |
| 4 | 6 |
| 5 | 10 |
| 100 | 4,950 |

This quadratic growth makes key management difficult in large networks.

Practical solution: Modern secure communication protocols commonly use asymmetric cryptography or key-agreement protocols to establish a shared secret, then use symmetric cryptography to protect bulk data.

Important distinction: Diffie–Hellman establishes a shared secret; it does not directly encrypt a message with a public key in the same way as RSA encryption.

## 3. Properties provided by cryptography

The lecture discusses four important security goals.

| Property | Meaning |
| --- | --- |
| Confidentiality | Only authorized parties can read the information. |
| Authentication | Verifies the claimed identity or source of a message. |
| Integrity | Detects unauthorized modification of data. |
| Non-repudiation | Provides evidence supporting a claim that a particular party signed a message. |

These properties depend on the cryptographic mechanism and how it is implemented.

For example, encryption alone does not necessarily guarantee integrity. Modern systems often use authenticated encryption or combine encryption with a message authentication mechanism.

### Alice, Bob, and Eve

- Alice: The sender.
- Bob: The receiver.
- Eve: An attacker who attempts to intercept or manipulate communication.

Suppose Alice sends Bob a stock-buy request. Bob later denies receiving it.

If Alice has a properly verified digital signature from Bob acknowledging receipt, that signature can provide evidence that Bob's private key was used to sign the acknowledgement. This is stronger evidence than an ordinary email header.

However, non-repudiation is not absolute: stolen keys, implementation flaws, and other circumstances can affect the strength of the evidence.

## 4. Evolution of symmetric encryption

### DES and AES

DES — Data Encryption Standard

- Uses a 56-bit effective key.
- Became vulnerable to brute-force attacks as computing power improved.
- Is no longer considered secure for modern applications.

AES — Advanced Encryption Standard

- Based on the Rijndael algorithm.
- Standardized in 2001.
- Supports 128-, 192-, and 256-bit keys.
- Widely used in modern secure communication and data protection.

The lecture explains why DES became inadequate: its 56-bit key provides only

$$
2^{56}\approx 7.21\times10^{16}
$$

possible keys, making exhaustive search increasingly practical with specialized hardware.

Double DES was not a satisfactory long-term solution because meet-in-the-middle attacks reduce its expected security. Triple DES improved security but was slower and has since been deprecated for modern use.

## 5. Public-key cryptography and RSA

Public-key cryptography uses two related keys.

- Public key: Shared with other participants.
- Private key: Kept secret by its owner.

### How public-key encryption works

Suppose Alice wants to send Bob a confidential message.

1. Bob publishes his public key.
2. Alice encrypts the message using Bob's public key.
3. Alice sends the ciphertext to Bob.
4. Bob decrypts it using his corresponding private key.

The goal is that someone who intercepts the ciphertext cannot feasibly recover the plaintext without the private key.

### RSA algorithm

RSA relies on properties of modular arithmetic and the difficulty of factoring a suitably generated large composite integer.

The basic steps are:

1. Choose two large distinct primes $p$ and $q$.
2. Compute

$$
n=pq
$$

3. Compute Euler's totient:

$$
\varphi(n)=(p-1)(q-1)
$$

4. Choose $e$ such that

$$
\gcd(e,\varphi(n))=1
$$

5. Compute $d$, the modular inverse of $e$:

$$
ed\equiv1\pmod{\varphi(n)}
$$

The resulting keys are:

- Public key: $(e,n)$
- Private key: $(d,n)$

For a suitably encoded message represented by integer $m$, basic RSA encryption is:

$$
c=m^e\bmod n
$$

Decryption is:

$$
m=c^d\bmod n
$$

The security of RSA depends on appropriate key sizes, secure implementation, and proper padding. Textbook RSA by itself is not secure for practical encryption.

### Other public-key techniques

- Diffie–Hellman: Establishes a shared secret over a public channel.
- ElGamal: Supports public-key encryption and related cryptographic constructions.
- Elliptic-curve cryptography (ECC): Provides efficient public-key techniques based on elliptic-curve mathematics.

Important correction to the lecture: Conventional ECC and RSA are both vulnerable to sufficiently capable fault-tolerant quantum computers. ECC is not quantum-safe; post-quantum cryptographic algorithms are designed to resist known quantum attacks.

## 6. Cryptographic hash functions

A cryptographic hash function takes input of arbitrary length and produces a fixed-length output, called a hash or digest.

$$
H:\{0,1\}^{*}\rightarrow\{0,1\}^{256}
$$

For example, SHA-256 produces a 256-bit digest regardless of the input's length.

Input data

Text, file, transaction, or block

Cryptographic hash function

Example: SHA-256

256-bit digest

64 hexadecimal characters

### Three key properties of a secure hash function

#### 1. Collision resistance

A collision occurs when two different inputs produce the same hash:

$$
x\ne y \quad \text{but} \quad H(x)=H(y)
$$

Collision resistance means that finding such a pair should be computationally infeasible.

Collisions must exist mathematically because there are infinitely many possible inputs but only finitely many possible outputs.

#### 2. Hiding property

Given a hash output, recovering its original input should be computationally infeasible, provided the input has sufficient uncertainty.

This property is particularly important when inputs contain high-entropy random values.

A hash is not encryption: it has no decryption key and is not designed to recover the original message.

#### 3. Puzzle friendliness

Given a target condition involving a hash and a known part of its input, it should be difficult to find an input satisfying that condition without trying many candidates.

This property is important for proof-of-work mining in systems such as Bitcoin.

### Applications of hash functions

- Detecting data modification.
- Verifying downloaded files.
- Identifying previously seen files.
- Building blockchain links.
- Creating transaction identifiers.
- Supporting Merkle trees and proof-of-work.

### SHA-256, SHA-3, MD5, and SHA-1

| Algorithm | Output length | Modern security status |
| --- | --- | --- |
| MD5 | 128 bits | Broken for collision resistance |
| SHA-1 | 160 bits | Broken for collision resistance |
| SHA-256 | 256 bits | Widely used and considered secure for general cryptographic hashing |
| SHA-3-256 | 256 bits | Widely standardized secure hash function |

SHA-256 is used extensively in Bitcoin. SHA-3 is a separate hash-function family, not simply a newer version of SHA-256.

### The birthday effect

For an ideal $b$-bit hash, generic collision search takes approximately $2^{b/2}$ hash evaluations.

For SHA-256, this is approximately:

$$
2^{128}
$$

This is why a 256-bit hash is generally considered to offer about 128 bits of collision security against generic attacks.

By contrast, finding an input matching a specific hash output generally requires approximately $2^{256}$ attempts in the idealized preimage-resistance model.

## 7. How hash functions protect data integrity

Suppose a software developer publishes a file and its expected hash.

1. You download the file.
2. Your computer computes the file's hash.
3. You compare the computed hash with the trusted expected hash.
4. If the hashes differ, the file does not match the expected content.

If they match, this provides strong evidence that the file is unchanged, assuming a secure hash function and a trustworthy reference hash.

Important: A hash alone does not prove who created a file. An attacker who can replace both the file and its expected hash may defeat this simple check. Digital signatures and authenticated distribution channels help establish trust in the expected hash.

## 8. Hash puzzles and proof of work

In proof-of-work systems, a miner tries different candidate values until the hash of the relevant block data satisfies a specified target.

For example, a simplified puzzle might require:

$$
H(\text{block data}\parallel x)<T
$$

where:

- $H$ is the hash function.
- $x$ is a candidate nonce.
- $\parallel$ denotes concatenation.
- $T$ is the target threshold.

The miner changes $x$ and computes the hash repeatedly until the condition is met.

A lower target generally means a harder puzzle.

The central property is that finding a valid solution should be computationally expensive, while checking a proposed solution should be relatively easy.

In Bitcoin, the proof-of-work condition uses the double SHA-256 hash of the block header, interpreted as an integer and compared against a target.

## 9. Hash pointers

A conventional pointer identifies a memory location. A hash pointer conceptually identifies data and includes the hash of that data.

It provides two important capabilities:

- Reference: Identifies the expected data by its hash.
- Integrity verification: Allows the data to be checked against that hash.

### How hash pointers form a blockchain

Block 1 — Genesis block

Data + initial reference

Hash of Block 1

Block 2

Data + previous block's hash

Hash of Block 2

Block 3

Data + previous block's hash

Each block stores the hash of the preceding block, creating a chain of references.

### Why is a blockchain tamper-evident?

Suppose an attacker modifies the data in Block 1.

1. The hash of Block 1 changes.
2. Block 2's stored previous-block hash no longer matches.
3. Changing Block 2 changes its hash as well.
4. Subsequent blocks must also be modified to restore consistency.

In proof-of-work blockchains, modifying historical blocks also requires recreating the associated proof of work and catching up with the accepted chain under the network's consensus rules.

This makes tampering increasingly difficult, but not mathematically impossible. Security depends on the consensus protocol, network conditions, and the attacker's resources.

## 10. Merkle trees

A Merkle tree is a tree-shaped data structure in which leaf nodes represent data items or their hashes, and parent nodes contain hashes derived from their children.

It allows efficient verification that a particular item belongs to a larger dataset.

### Example of a Merkle tree

Root hash

H(H12 ∥ H34)

H12

H(H1 ∥ H2)

H34

H(H3 ∥ H4)

H1

H2

H3

H4

H1–H4 are hashes of four individual data items.

For four data items:

$$
H_1=H(D_1),\quad H_2=H(D_2)
$$

$$
H_{12}=H(H_1\parallel H_2)
$$

Similarly:

$$
H_{34}=H(H_3\parallel H_4)
$$

The root is:

$$
R=H(H_{12}\parallel H_{34})
$$

### Advantages of Merkle trees

- Efficient membership verification.
- Detection of changes to individual data items.
- Compact proofs of membership.
- Efficient verification for very large datasets.

For a balanced binary Merkle tree containing $n$ leaves, the proof of membership generally requires approximately:

$$
O(\log_2 n)
$$

sibling hashes.

For example, with 1,024 data items, a membership proof typically requires only 10 sibling hashes, rather than hashing every item individually.

A standard Merkle tree does not automatically provide efficient non-membership proofs; additional structure, such as a sorted Merkle tree, may be needed.

### Merkle trees in practice

The lecture describes Estonia's Keyless Signature Infrastructure (KSI) as an example of using hash-based structures to support the integrity and verification of records.

The central idea is to aggregate many records into hash trees, retain or publish their root hashes, and use these roots as evidence that the records have not been silently altered.

## 11. Digital signatures

Digital signatures allow a person or account to authorize a message or transaction in a way that other participants can verify using the corresponding public key.

A digital signature system generally has three functions:

1. Key generation: Creates a public/private key pair.
2. Signing: Uses the private key to sign a message or its digest.
3. Verification: Uses the public key to check the signature.

Conceptually:

$$
(sk,pk)\leftarrow\operatorname{KeyGen}()
$$

$$
\sigma=\operatorname{Sign}(sk,M)
$$

$$
\operatorname{Verify}(pk,M,\sigma)=\text{true}
$$

Here, $sk$ is the secret key, $pk$ is the public key, and $\sigma$ is the signature.

In practical digital signature algorithms, signing is not simply encrypting a message with the private key and decrypting it with the public key. That is an oversimplification sometimes used in introductory explanations.

### What digital signatures provide

- Authentication of the signing key.
- Integrity of the signed message.
- Evidence of authorization by the holder of the private key.
- Support for non-repudiation.

A signature does not automatically establish the real-world identity of the key holder. The association between a key and a person or organization must be established separately where required.

### Digital signatures in Bitcoin

Bitcoin uses the Elliptic Curve Digital Signature Algorithm (ECDSA) in traditional transaction-signature contexts, with Schnorr signatures also supported for Taproot spends.

Private keys must be protected because someone who obtains a private key may be able to authorize transactions associated with it.

Good randomness is crucial for ECDSA nonce generation; nonce failures can expose the private key.

## 12. Public keys as blockchain identities

In permissionless blockchain systems, users can generate cryptographic key pairs without registering a conventional username with a central authority.

The public key, or an address derived from it, can be used to identify an account or destination for transactions.

A simplified model is:

- Public key or derived address = publicly shareable identifier.
- Private key = secret credential used to authorize operations.

This enables participation without requiring every user to reveal their real-world identity.

### Is Bitcoin anonymous?

Bitcoin is generally described as pseudonymous, rather than fully anonymous.

Although an address does not directly reveal a person's real-world identity, the public ledger records transactions and their relationships. Analysis of transaction patterns, address reuse, and information obtained outside the blockchain can sometimes connect addresses to individuals or organizations.


