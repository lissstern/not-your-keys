# not-your-keys
Blockchain Private Key Vulnerability List

## Bitcoin

* **[Milk Sad Disclosure](https://milksad.info/disclosure.html)** - July 2023, a cryptographic weakness discovered in the widely utilized Libbitcoin Explorer (bx) cryptocurrency wallet tool where a bad PRNG algorithm, seeded with only 32 bit of system time, used to generate private keys. Additionally, the close similarities with another actively exploited vulnerability in Trust Wallet are described, and provided some background on the Libbitcoin Explorer context and overall timeline. **Results**: confirmed the practical use of the weak function for over 2600 cryptocurrency wallets on the Bitcoin Mainnet.

* **[Polynonce: A Tale of a Novel ECDSA Attack and Bitcoin Tears](https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/)** - September 2022, a test attack against ECDSA in the fact to define a recurrence relation among nonces used in different ECDSA signatures as a polynomial of arbitrarily high degree. This attack means is that every time an ECDSA signature is generated, the signature itself gives us a relation between the nonce and the private key. If the nonces are truly randomly generated, this should never be a problem, but nonces are usually output by a pseudorandom number generator (PRNG) rather than being really random, and PRNGs are deterministic algorithms with relatively low complexity. **Results**: 773 broken bitcoin wallets, all have zero balance because they have already been hacked in the past. None of recurrence nonces in the Ethereum.

* **[Malicious Bitcoin Wallet Generation Software Could Produce Known Private Keys](https://pastebin.com/jCDFcESz)** - November 2017, an evidence that some bitcoin address generation code in the wild is using private keys that can easily be discovered on a regular basis. Experiment: to see if anyone used a block hash as a private key, addresses that were generated from the merkle root used as a private key, repeated Sha256 on words, siphoning bitcoin from some service on a regular basis. **Results**: there are 100+ addresses that received bitcoins whose private keys are the bytes resulting from Sha256 of another public address.

* **[Recovering Bitcoin private keys using weak signatures from the blockchain](https://web.archive.org/web/20130314180507/http://www.nilsschneider.net/2013/01/28/recovering-bitcoin-private-keys.html)** - January 2013, discovered a potential weakness in some Bitcoin implementations. ECDSA requires a random number for each signature. If this random number is ever used twice with the same private key it can be recovered. This transaction was generated by a hardware bitcoin wallet using a pseudo-random number generator that was returning the same “random” number every time. **Results**: over 285 bitcoin addresses compromised. [Forum Discussion](https://bitcointalk.org/index.php?topic=581411.0), [Proof of concept](https://github.com/daedalus/bitcoin-recover-privkey).

## Ethereum

* **[Finding Over 732 Active Private Keys On Ethereum's Blockchain](https://www.ise.io/casestudies/ethercombing/)** - April 2019, focus on eight 32-bit “sub-regions” in the 256-bit key space where are likely to observe Ethereum addresses in use that have resulted from a weak private key. This gives eight regions with a possible 2^32 -1 (i.e., ~4.3 billion) combinations per region. The above key space ranges, while making up an infinitesimal part of the 256-bit key space, are some areas that private keys might exist in due to errors or other factors compromising randomness of a 256-bit key. **Results**: discovered 49,060 transactions spread over 732 public keys for which the private key was found, with a total transfer amount of more than 32 Ethereum.

## Funny Stories

* **[A Glimpse of the Deep: Finding a Creature in Ethereum's Dark Forest](https://www.bertcmiller.com/2021/12/28/glimpse_nonce_reuse.html)** - December 2021.
* **[How I checked over 1 trillion mnemonics in 30 hours to win a bitcoin](https://medium.com/@johncantrell97/how-i-checked-over-1-trillion-mnemonics-in-30-hours-to-win-a-bitcoin-635fe051a752)** - June 2020.


## Tools & Data

* **[Vanitygen](https://github.com/samr7/vanitygen)** - a command-line vanity Bitcoin address generator.
* **[Bitaddress](https://www.bitaddress.org)** - open source JavaScript client-side Bitcoin online wallet generator.
* **[LoyceV's](https://bitcointalk.org/index.php?topic=5265993.0)** list of all Bitcoin addresses ever used.
* **[Blockchair](https://blockchair.com/dumps)** - database dumps for Bitcoin, BitcoinCash, Dogecoin, Ethereum, Dash, Litecoin and Zcash.
* **[Quicksync](https://quicksync.io/)** - Cosmos networks blockchain states compressed archives: Cosmos/ATOM, Kava, Osmosis, Terra, Axelar etc.
* **[Btcrecover](https://github.com/gurnec/btcrecover)** - open source Bitcoin wallet password and seed recovery tool.
* **[Hashcat](https://github.com/hashcat/hashcat)** - CPU/GPU world's fastest and most advanced password recovery utility.
