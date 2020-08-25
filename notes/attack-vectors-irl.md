# Attack Vectors IRL: What It REALLY Means To Be Your Own Bank 

11:00am - 11:30am PT
Jameson Lopp, co-Founder of CASA:

There is a reason banks exist: banks specialize in security.
To achieve the promise of 'being your own bank', how can it be made feasible to have the same level of security (if not better) as a bank

Bitcoin's Greatest Strength:
- no authority can confiscate your money or censor your transactions

Bitcon's Greatest Weakness:
- no authority can return your money if it's lost or stolen


Threat Landscape

Physical Coercion -- aka Wrench Attacks 
- https://github.com/jlopp/physical-bitcoin-attacks/blob/master/README.md
- 50-60 attacks that Lopp is aware of
- attackrs were successful in transferring money
- some people defended themselves (escaped or fought)

Prevention of physical attacks requires strong opsec
Only fullproof way to prevent coercion is to not access your keys.

## Issues

### Hardware Flaws
- side-channel attacks
- voltage-glitching

### Brain Wallets:
- common phrases just get hacked
- humans are bad at generating entropy (which brain wallets rely on)

### Malware
- malware focused on stealing bitcoin
  - e.g. clipboard malware

### Malicious Tor Relays
- https://twitter.com/JohnNaulty/status/1292616693701804033

### Malicious QR Encoder

### Malicious Mixers
  - do it yourself, join market, wasabi, samouri

### Malicious Wallet Software
- opensource project "Wallet Generator"
- sufficiently obfuscated

### SIM Swapping
- https://medium.com/coinmonks/the-most-expensive-lesson-of-my-life-details-of-sim-port-hack-35de11517124

### Social Engineering

- phishing with adwords
- typosquatting
  - domain name service level
  - software packages
- fake airdrops

## Bitcoin's greatest threat

- The User:
  - lost bitcoins
    - password reuse
  - data loss

Paper wallets
- hard to generate private keys securely (do you trust your printer, really?)
- loss to physical attackers if unecnrypted
- loss due to environmental factors (moisture, fire)
- loss due to improper transaction
  - not fully sweeping wallet

metal wallets
- loss to physical attackers if unencrypted
- loss due to environmental factors
- loss due to improper transaction construction + single key sweeping

[opsec] Don't make yourself a target
- first rule of bitcoin club is: always talk about bitcoin
- second rule of bitcoin club is never talk about _your_ bitcoin

Inheritance
- complexity can lead to failure
- CASA has inheritance setup


## Advice

- use hardware devices _whenever_ possible

