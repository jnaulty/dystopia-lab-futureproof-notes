# The Nuance of the Nonce - Data Analysis of the Blockchain

```

2:30pm - 3:00pm PT
Kristy-Leigh, Prev CTO at Core Scientific & Genesis Mining
The Nuance of the Nonce - Data Analysis of the Blockchain

```

### What is a Nonce?

- pseudorandom number utilized as a counter
- used in the creation of a block of transactions as a modifier for the sha256 hash function
  - only one nonce accepted per block 
  - in theory, nonce values should be at random
    - 2010-2016 theory held true
      - may 2016, four white 'bands' begin to form where nonces are less random 
      - S9 was announced on May 31st, 2016 and shipped mid-june (mining hardware)
      - same thing happened for monero
    - started analysis of nonces across mining pools 
      - bitfury very uncommon
      - asic pattern across most other miners

### Fingerprint individual devices with this data

- applied fingerprinting techniques to ethereum
- winning nonce distributiion appeared strongly uniform
  - some banding during cpu mining phase then eventually to gpu mining phase
  - analyze all 64 _individual_ bits fixed within the nonce, patterns emerge
    - due to hardware
      - pinpoint various miners e.g., e3 miners
    - due to software
      - claymore 
    - due to pools

### Ethereum Classic 51% Attack (v2)

#### Quick summary

ETC was hit by two 51% attacks one on july 31, 2020, and one on august 7, 2020 -- came from same attacker

Bitfury released report, breaking down attack

- hashrate was rented from "NiceHash"
- Initial attack (July 31) cost $192k USD and and took profit by $5.6 million USD
- Second attack (Aug 7) cost $172k USD and took profit of $1.7 million USD

Because PoW consensus boils down to having a chain with the 'most' work.
A 51% attack strategy is to mine on a private chain and try to get ahead of main chain (shadow chain) which then is broadcasted to all the nodes. The nodes then 'switch over' to this chain until the original 'non-private' chain

_extraData_ Field

All the blocks from the attack (as well as nearby blocks up to 24 hours before the attack) had the same _extraData_ value, which has never been used in the history of ETC or ETH.

Suspectected attacker address has been consistent miner in ETC network since 2017--represented on average of 2.5% of nethash.


- hardware + software developers want to keep track of usage of their product
  

### Node Unique Identification

Watch when miner's sell, heuristic for utility payment due
correlate with utility company collection dates across the world

### Q+A

Thinks bitcoin is 'too big' to be attacked. 

([tool for 51% attacks](https://www.crypto51.app/coins/BTC.html): Aug 22, bitcoin was around $540,000 to perform a 51% attack for an hour)

> are there any opensource tools one could use to scrape nodes/peer information for the ethereum network? Did you use any of these tools for your research?

Many tools out there, usually API based.
- Google's "Big Query" 
  - Ethereum + ETC node run by google
  - Reach out on Twitter for sample block extractor :)
    - shared this research paper [_Ethereum Analytics_ by Athina Voulgari](./resources/nonce-shadow-mining/Master_thesis-Athina_Voulgari.pdf)
- Pool explorer from MIT
- ForkWatch (looks for 51% attacks)


