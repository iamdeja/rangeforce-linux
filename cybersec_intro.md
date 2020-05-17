# Introduction to cybersecurity <!-- omit in toc -->

> Note: _pdf version may not be up to date_

- [Concepts](#concepts)
  - [Information security](#information-security)
    - [Availability](#availability)
    - [Integrity](#integrity)
    - [Confidentiality](#confidentiality)
  - [Security of data](#security-of-data)
  - [Standard model of harm](#standard-model-of-harm)
  - [Security and planned residual risk](#security-and-planned-residual-risk)
    - [Acceptable residual risk](#acceptable-residual-risk)
  - [Security threats](#security-threats)
    - [Classification](#classification)
    - [Threats classified by source](#threats-classified-by-source)
- [Attacks](#attacks)
  - [Sources of attacks](#sources-of-attacks)
  - [Channels of attack](#channels-of-attack)
  - [Attack classifications](#attack-classifications)
    - [Physical attacks](#physical-attacks)
    - [Mis-use of resources](#mis-use-of-resources)
    - [Blocking of resources](#blocking-of-resources)
    - [Interception](#interception)
    - [Fabrication](#fabrication)
    - [System manipulation](#system-manipulation)
    - [Attacks to security mechanisms](#attacks-to-security-mechanisms)
    - [Attacks via software](#attacks-via-software)
- [Vulnerabilities](#vulnerabilities)
  - [Infrastructure related vulnerabilities](#infrastructure-related-vulnerabilities)
  - [IT related vulnerabilities](#it-related-vulnerabilities)
  - [Personnel related vulnerabilities](#personnel-related-vulnerabilities)
  - [Organisational vulnerabilities](#organisational-vulnerabilities)
  - [Interaction between threats and vulnerabilities](#interaction-between-threats-and-vulnerabilities)
- [Digital data](#digital-data)
  - [Securing digital data](#securing-digital-data)
  - [Role of cryptography](#role-of-cryptography)
  - [Availability of digital data](#availability-of-digital-data)
  - [Integrity of digital data](#integrity-of-digital-data)
  - [Confidentiality of digital data](#confidentiality-of-digital-data)
- [Safegurads](#safegurads)
  - [Classification of safeguards](#classification-of-safeguards)
  - [Purpose divided safeguards](#purpose-divided-safeguards)
    - [Preventive safeguards](#preventive-safeguards)
  - [Identifying safeguards](#identifying-safeguards)
    - [Operative identification](#operative-identification)
    - [Post-event identification](#post-event-identification)
    - [Evidence-based identification](#evidence-based-identification)
  - [Reconstructive safeguards](#reconstructive-safeguards)
  - [Classification by IT assets](#classification-by-it-assets)
  - [Classification by implementation](#classification-by-implementation)
    - [Organisational safeguards](#organisational-safeguards)
    - [Physical safeguards](#physical-safeguards)
    - [IT-related safeguards](#it-related-safeguards)
- [Risk management](#risk-management)
- [Symmetric cryptoalgorithms](#symmetric-cryptoalgorithms)
  - [Role of symmetric keys](#role-of-symmetric-keys)
  - [Fields of use of symmetric cryptoalgorithms](#fields-of-use-of-symmetric-cryptoalgorithms)
  - [Major symmetric cryptoalgorithms](#major-symmetric-cryptoalgorithms)
  - [Block and stream ciphers](#block-and-stream-ciphers)
  - [Inner structure of block ciphers](#inner-structure-of-block-ciphers)
    - [Main basic operations inside rounds](#main-basic-operations-inside-rounds)
  - [AES](#aes)
    - [AES breaking machine](#aes-breaking-machine)
    - [Implementation of AES](#implementation-of-aes)
- [Asymmetric cryptoalgorithms](#asymmetric-cryptoalgorithms)
  - [RSA](#rsa)
    - [Mathematical background of RSA](#mathematical-background-of-rsa)
    - [RSA key-pair generation](#rsa-key-pair-generation)
    - [RSA ciphering](#rsa-ciphering)
    - [Main concepts of RSA](#main-concepts-of-rsa)
    - [Cryptanalysis of RSA](#cryptanalysis-of-rsa)
  - [Other asymmetric algorithms](#other-asymmetric-algorithms)

## Concepts

### Information security

> Other names: _data security, cyber security_

Information security consists of three independent branches:

- information availability
- information integrity
- information confidentiality

Each of these three branches must be maintained for all information (data).

#### Availability

Data availability ensures the timely and convenient access to data for all authorised entities.

#### Integrity

Data integrity ensures that the information comes from a legitimate source and hasn't been altered, deliberately or accidentally, after its creation.

#### Confidentiality

Data confidentiality ensures that data, or the information carried by the data, can be accessed only by authorised subjects.

### Security of data

Security of data is achieved by securing the IT assets surrounding the data. These assets include

- IT equipment
- data communication channels
- software

and must take into account

- the organisation (structure and operating principles)
- personnel
- data carriers
- infrastructure

### Standard model of harm

**Threats** influence the data and exploit the **vulnerabilities** of IT assets or components of the systems. Threats in conjunction with vulnerabilities determine and pose the **security risk**.

When a risk is not mitigated, a **security breach** may happen. Therefore, to minimise risks and avoid breaches, **safeguards** or **security measures** must be set in place.

### Security and planned residual risk

No matter the amount of safeguards set in place, absolute security can never be achieved. Implementation of safeguards merely minimises the probability of a breach.

#### Acceptable residual risk

Instead of absolute security, the concept of acceptable residual risk is followed.

Acceptable residual risk means the situation where the total price of all implemented safeguards is approximately equal to the forecast of loss caused by a security breach.

### Security threats

A threat represents a potential violation of security by an external element. It may consist of

- violation of availability
- violation of integrity
- violation of confidentiality

or any combination of those. A threat is always considered an external influence.

#### Classification

Threats can be classified by

- the target: availability, integrity, confidentiality
- the source: subject causing potential harm
- the type of IT asset
- the extent of potential danage

Generally the first two classifications are used.

#### Threats classified by source

Threats classified by source can be separated in two groups:

##### Spontaneous or accidental threats <!-- omit in toc -->

such as environmental threats (Force Majeure), technical failures or human error,

##### Deliberate acts or attacks <!-- omit in toc -->

in case the damage is intentional or the motives are clear.

It is worthy of note that in practice, accidental or spontaneous threats cause in general more harm than deliberate attacks, due to neglicence.

## Attacks

Attacks or deliverate acts are always based on humans making deliberate actions to harm an entity's security.

### Sources of attacks

- Authorised users of IT systems
- Intelligence agents
- Crackers
- Other criminal elements

### Channels of attack

- Direct contact with the target system
- Networks
- Portable data carriers such as external memory devices

### Attack classifications

- physical attacks
- mis-use of resources
- blocking of resources
- interception
- fabrication
- system manipulation
- attacks to security mechanisms
- attacks via software / malware

#### Physical attacks

Physical attacks mainly harm the integrity and availability.

- attacks on infrastructure
- vandalism
- trespassing / break-in
- theft
- manipulation or destruction of equipment

#### Mis-use of resources

Mis-use of resources harms all branches of security.

- unauthorised use of IT systems
- mis-use of user rights
- mis-use of administrator privileges
- theft of services (such as mobile services)

Resource misuse is susceptible to happen during the conversion, maintenance, repairing and/or upgrade tasks performed by external parties.

#### Blocking of resources

Blocking of resources mainly harms availability.

- overloading of network
- mass-execution of tasks
- filling quotas

The most common implementation of resource blocking are distributed denial of service (DDOS) attacks.

#### Interception

Interception or eavesdropping is an attack to confidentiality by any unauthorised subject.

- voice interception in rooms
- interception of calls
- unauthorised reading or copying of data
- reading of residual information (ex: from printers)
- wiretapping
- inappropriate deletion of data or destructuring with subsequent reading

#### Fabrication

Fabrication or faking consits in fake data inputs or propagation, which harms integrity.

- playback of recordings out of context
- masquerade attacks (phishing)
- social engineering
- denial of authorship

#### System manipulation

Manipulation consists in unauthorised changes made to an IT system, which mainly harms integrity. It has some overlaps with fabrication.

- manipulation of data or software
- manipulation of communication lines
- manipulation of data during transfers
- attacks via service ports

#### Attacks to security mechanisms

Attacks to security mechanisms can harm all three branches of information security.  
The main attack targets are authentication systems and cryptosystems.

#### Attacks via software

- malware
- undocumented features of legitimate software
- special purpose software

##### Malware <!-- omit in toc -->

- logical bombs
- trojan horses
- worms
- viruses
- droppers (trojan installers)

## Vulnerabilities

Vulnerabilities are all properties of a system which can be exploited by threats. They can be divided in four main classes:

- infrastructure vulnerabilities
- IT vulnerabilities
- personal-related vulnerabilities
- organisational vulnerabilities

### Infrastructure related vulnerabilities

- unfavourable physical locations of devices
- primitive or deprecated infrastructure solutions

### IT related vulnerabilities

- limited resources
- improper installation of equipment or connection lines
- errors, defects and undocumented features of software
- shortcomings of protocols
- shortcoming of data management
- inconvenience of safeguards

### Personnel related vulnerabilities

- incorrect procedures
- ignorance and lack of motivation
- ignoring of safeguards and protocol (intentional and negligence)

### Organisational vulnerabilities

- deficiencies of work organisation
- shortcomings of resource management
- incomplete documentation
- incomplete implementation of safeguards
- shortcomings of safeguard management

### Interaction between threats and vulnerabilities

Threats exploit vulnerabilities.

Security diminishes as the probability of threats increases and so does the number of exploitable vulnerabilities. The reciprocal stands as well.

## Digital data

### Securing digital data

Cryptography is essential for achieveing both confidentiality and integrity, which differs significantly from paper based data.

Authentication itself becomes essential and availability is often ensured by the network.

### Role of cryptography

Encryption or cyphering is a technique where data is converted to a non human readable or device interpretable form. The conversion process uses a certain piece of data called a key to achieve the encryption.

Cryptography is used both for

- ensuring confidentiality: data cannot be deciphered without the key
- ensuring integrity: data cannot be changed without having access to the decryption key or leaving a permanent mark that data was altered

### Availability of digital data

- regular backups
- reliable IT systems
- digital record management system
- transmission of data via networks

### Integrity of digital data

- data and its carrier are permanently tied together (excludes network based applications)
- client-server techniques where interacrtions are logged
- usage of e-signatures to cryptographically associate data and its creator

### Confidentiality of digital data

- secure storage and transport of plaintext data
- encryption of data and public handling

Encryption adds the **key management** problem. Additionally, encryption should be mandatory for any confidential information transfers over the common network.

## Safegurads

Safeguards minimise vulnerabilities and the residual risk.

### Classification of safeguards

- their purpose
- their security area
- the type of assset
- the means of implementation
- strength of security

### Purpose divided safeguards

- preventive safeguards
- identifying safeguards
- reconstructive safeguards

Safeguards may also be polyfunctional.

#### Preventive safeguards

Preventive safeguards are used to prevent security incidents such as

- to minimise vulnerabilities
- to prevent attacks
- to minimise risk probabilities
- to decrease the potential damage of attacks
- the facilitate reconstruction

Preventive safeguards can further be divided into three subcategories

##### Reinforcable safeguards <!-- omit in toc -->

which have the purpose of minimising the impact of spontaneous threats

- order or systematicness (standards, procedures, ...)
- working conditions (micro-climate, ergonomics, social climate, corporate hierarchy)
- preventive checks (verification and testing, monitoring, auditing)
- security awareness (training of employees, security drills, ...)

##### Deterring / scaring safeguards <!-- omit in toc -->

which have the purpose of minimising the probability of attack attempts,

##### Separative safeguards <!-- omit in toc -->

which fend off the attacks by taking care of different security aspects. They can further be divided into

- spatial isolation
- temporal isolation
- logical isolation (access control, service broker, securing)

### Identifying safeguards

#### Operative identification

Involves methods which are able to identify security incidents as soon sa they occur and allow for immediate response.

#### Post-event identification

Is based on logging of events and later analysis of the logs for future improvement or proof and action taking.

#### Evidence-based identification

Is based on security elements integrated to IT assets which allows to check for integrity and/or confidentiality of data.

### Reconstructive safeguards

After a security incident, it is necessary to restore the normal operation of impacted IT systems. This can be achieved via

- backups (data redundancy)
- renovation (removing of defects and errors)
- replacing (substitute for corrupted or damaged data)

### Classification by IT assets

German BSI IT Baseline Security Method and Estonian ISKE standard distinguish the following categories:

- generic aspects
- infrastructure
- IT systems
- networks
- applications

### Classification by implementation

#### Organisational safeguards

which include the security of administration, of system design, management and security incident handling activities and operations.

They should be implemented in the first order and beginning with security policies formulation, risk analysis and security plan creation.

They also should include four main components:

- activities a person must do
- activities which are prohibited for a certain person
- consequences of frobidden actions
- consequences of negligence

#### Physical safeguards

which involves the infrastructure, mechanical components, guards, etc...

#### IT-related safeguards

which are mainly used for performing logical separations and identifications of security incidents.

Two main branches include software-based access control and cryptographic means.

## Risk management

The main goal of risk management is the exact implementation of a set of safeguards.

## Symmetric cryptoalgorithms

Secret key cryptoalgorithms or symmetric cryptoalgorithms are methods where the same secret key is used both for ciphering and deciphering. They are considered practically secure if they satisfy both conditions:

- the key is at least 128bits long
- there aren't any known effectice cryptoanalytic methods

### Role of symmetric keys

Keys should always be generated separately: they are not created by encryption or decryption algorithms. Key lengths are determines by the algorithms of key generation themselves. Finally, any bit sequence of predefined length can be considered as a cryptographic key.

> The minimal keylength should be at least 128bits (16bytes) to counter exhaustive search methods.

### Fields of use of symmetric cryptoalgorithms

- Transmission of confidential information using unsafe networks
- Secure storage of confidential data
- Secure erasing of data (rewrites)
- Creation of secure key materials for cryptographic use

### Major symmetric cryptoalgorithms

The DES key generation algorithm is considered insecure due to its keylength being only 56bits. 3DES or triple mode DES was used until 2005.

AES is still considered an excellent algorithm for mainstream use since it won the 2001 NIST commercial symmetric cryptoalgorithms competition. It is still a _de facto_ standard and it is estimated that 80%-85% of symmetric cryptoalgorithm usage involves AES. Common keylengths are 128, 192 and 256bits.

IDEA (128bits) originated in the late 1080s in Switzerland. FOX and IDEA NXT were published in 2003 with keylengths ranging from 0 to 256bits.

Blowfish with a variable keylength of up to 448bits was made by Bruce Schneider in the 1990s.

RC4 is a stream cipher with a keylength between 40 and 256bits and was created in 1987. It is considered too weak for modern use however.

### Block and stream ciphers

Symmetric cryptoalgorithms can be divided into block and stream ciphers, with the former being more widespread than the latter.

#### Block ciphers <!-- omit in toc -->

Block ciphers are used in methods where plaintext is divided into blocks of certain length and these block are encrypted separately.

Popular modes include:

- electronic codebook mode: ECM
- cipher block chaining mode: CBC
- K-bit cipher feedback mode: CFB
- K-bit output feedback mode: OFB

Cipher and output feedback modes are used in situations where some form of feedback needs to be organised.

##### ECM <!-- omit in toc -->

Plainext blocks are encrypted independently from each other using the same secret key. The disadvantage is that each ciphertext block depends on only one plaintext block, which can cause repeats in ciphertext.

##### CBC <!-- omit in toc -->

Before encrypting subsequent blocks, the result of the previous block is XORed with the plaintext. As an advantage, one block of ciphertext depends on all previous plaintext: there will be no repeats in ciphertext.

##### CFB <!-- omit in toc -->

The feedback loop involves both block ciphers and XORing.

##### OFB <!-- omit in toc -->

The feedback loop involves only the cipher block which recursively originates from a certain value, using the initial key.

#### Stream ciphers <!-- omit in toc -->

Stream ciphers are used in methods where a key sequence is generated from a given secret key, and a traditional XOR process is used to cipher all of the plaintext.

#### Usage of different block cipher modes <!-- omit in toc -->

ECMs are the most convenient, albeit not secure enough modes to encrypt long plaintexts, therefore the most used method is the CBC mode.  
Feedback modes are less frequently used but allow the usage of block ciphers as stream ciphers in order to produce key sequences, and are therefore mainly used for secure erasing of data.

### Inner structure of block ciphers

Block ciphers usually involve numerous transformations of plaintext called **rounds**, where the output of a previous round is the input for the next one. The way different rounds use keys is determined by a **key sequence algorithm**. In case such an algorithm is missing, the original key gets used, however, if it does exist, the **round keys** are computed from the initial key.

#### Parameters of typical block ciphers <!-- omit in toc -->

- length of a key
- length of a block
- number of rounds
- presence (or absence) of a key sequence algorithm
- number of round keys
- length of round keys

#### Main basic operations inside rounds

- substitution - replacing of original characters by other ones
- transposition / permutation - changing the order of characters

Most transformations within a block are comprised of a combination of the two basic operations.

### AES

DES is a block cipher with a block length of 64bits and key length of 56bits. It was internationally standardised and made available form FIPS PUB 46-s, however, it was already weakening by the end of the 1990s due to the short keylength. A competition for a new standard was launched, and thus AES was created.

AES must be a block cipher with a block length of at least 128bits and having 3 different possible keylengths: 128, 192 and 256bits. In AES, they key length and the block length are the same. For a 128bit key, 10 rounds are involved, 12 rounds for 192bit keys and 14 rounds for 256bit keys. It is noteworthy that there is no key sequence algorithm used.

Each round consists of four subsequent different type of transformations:

- byte subs
- row shifts
- column mixes
- round key adding

#### Cryptanalysis of AES <!-- omit in toc -->

An exhaustive search would need to perform from 2^128 to 2^256 operations, which is practically infeasible. Moreover, no effective cryptanalysis methods are currently known to break AES encryption, making it practically secure.

However, in 2002, the surfacing of algebraic cryptanalysis did offer a way to potentially break 128bit AES with only 2^87 operations. However, in practice, algebraic cryptanalysis has not been yet implemented. Moreover, **related key attacks** where different mathematically related keys are used to brute force the algorithm, have also been conceived in theory only. Lastly, a theoretical **side channel attack** that is based on getting internal information from within the block has been conceived, but again, not implemented in practice.

#### AES breaking machine

A _breaking machine_ is a parallel computer that performes exhaustive searches where different key intervals are searched simultaneously with different chips. Such machine would break DES within one second, but would currently take thousands of millions of years to break AES. Moreover, such machines cost north of fifty thousand euros. Therefore, all three versions of AES are likely to remain practically secure for many more years.

#### Implementation of AES

AES can be realised both by software and hardware, however hardware computings are up to a few hundred times faster depending on the chips and programming languages used.

## Asymmetric cryptoalgorithms

Asymmetric or public-key cryptoalgorithms make use of two keys: one key is used for encryption, and the other for decryption. The same key cannot be used for both tasks. These keys are generated using algorithms that matemathically link them together in a way that it is practically impossible to derive one from the other. These keys are called public and private key.

The public key is usually known for all parties involved in the exchange, and can be made available to the public. A private key should however only be known to the author or owner of a key-pair.

Asymmetric algorithms are often used for key-exchange purposes, as they allow to exchange symmetric keys in a secure and encrypted manner. They are also used to sensure integrity of data, and lay the foundation to digital signature technologies.

As opposed to symmetric keys, arbitrary bitstreams cannot be consered valid keys, and therefore a special key generation algorithm is always required. However, such algorithms induce some form of information redundancy, therefore causing the need for significantly longer keys than symmetric ones to ensure practical security.

### RSA

RSA is the most widespread public-key cryptoalgorithm in the world today. It is considered practically secure for key-lengths no less than 2048 bits. For RSA, computing the public key from the private key is fairly easy, however it is practically infeasible to extract the private key from the public key. The security of RSA is guaranteed by the difficulty in factorising large numbers, solving the discrete logarithm problem.

RSA supports arbitrary keylengths, however the most widespread keys come in powers of 2 such as 2048, 4096, .... Keys less than 2048bit ones are however already considered to be weak.

#### Mathematical background of RSA

An algorithm is called of polynomial complexity if for a task of length _N_, the solution time is _N^k_ proportional with some fixed integer _k_. Polynomial algorithms are generally considered to be good algorithms since as _N_ increases, the solution time is not growing very fast.

Exponential complexity algorithms induce much worse solving times, as for a task of length _N_, the solution time is proportional to the value of _2^N_.

Non polynomial algorithms are considered practically unsolvable, which may either be good or bad, depending on usage case.

> Discrete logarithm problem: _find g, given a, n, p in a = g^n (mod p)_

Edmond's Postulate: an algorithm is considered to be good if its time complexity can be represented by a polynomial _O(n^k)_ from an input, with _k_ some integer. Polynomials are closed under addition and multiplication, in other words, the sum and/or product of polynomials is always a polynomial.

> Closure of polynomials: O(n^k) + O (n') = O(n^[max{k,l}]) | O(n^k) \* O(n') = O(n^[k+l])

#### RSA key-pair generation

Two large primes _p_ and _q_ are generated. Their product, the RSA module, is generated: _n = p \* q_. Then, _e_ is chosen in a way that it is relatively prime to _(p-1)(q-1)_. Finally, _d_ is chosen such that _d \* e = 1 mod (p-1)(q-1)_.

The pair _(n, e)_ is the public key, and the triple _(p, q, d)_ is the private key.

#### RSA ciphering

It is possible to encipher texts that are less than _pq_ bits. The enciphering process includes a discrete exponent: _Y = Cip(X) = X^d mod n_. Likewise for deciphering: _X = Decip(Y) = Y^e mod n_ since _(X^d)^e = X mod n_.

#### Main concepts of RSA

Without having a private key, a plaintext cannot be encrypted in a way that it is decipherable using a public key. Furthermore, a message encrypted with a public key cannot be decrypted using the public key again.

Conceptually, _e_ is a public exponent and _d_ is a secret exponent. Functions for which an inverse cannot feasibly be found are called _one-way functions_. If however, the inverse can be found with some minimal additional information, the function is called _trapdoor one way function_. RSA is an example of a trapdoor one-way function.

#### Cryptanalysis of RSA

Factorisation of 70 digit numbers take only a few minutes for average personal computers. In general, 100 digit numbers can still be factored at home in less than a day.

In 1996, the factorisation of a 140 digit number took 5 years and required a joint computational effort of many computers. To date, the largest factored number (2009) was 232 digits long.

A 300 digit number (1024bit RSA) would take millions of years using current classical computing methods and hardware.

### Other asymmetric algorithms

- elliptic curve based algorithms (P-384 or ED25519)
- El-Gamal
- DSS
- Paillier' system
