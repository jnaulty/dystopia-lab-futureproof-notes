
# Modern Bitcoin Transaction Signing On A Smartcard Chip

10:30am - 11:00am PT
Nicolas Bacca, co-Founder of Ledger:



### Smartcard Chips v. MCUs

- CPU runs more or less the same chip (ARM)
- Smartcard chips are 'hardened' against physical attacks (to prevent key extraction)
- development toolchain is fairly nonstandard (java card + GlobalPlatform)
- strong constraints on RAM for smartcard chip (10-50kb)
- smartcards are cheap (tens of cents)



### Service Deployment Strategies

#### smartcard chips
- load code at point of manufacturer
- no domain split between logic and secret 

### Composite Device (MCU + SE)
- domain split between logic + secret
- must guarantee link between MCU that is unprotected and link to Secure element is protected

Smartcard Cons
- non standard dev environments
- lack of manufacturers
- low ram + performance

Smartcard Pros 
- designed to protect against physical attacks
- validation of the platform (secrets + business logic in same security boundary)
- low price
- forced optimization ;)

## BTC transaction signing on hardware wallet
Host has:
- utxos
- HD key paths
- outputs
- PSBT (BIP174) - partially signed bitcoin transaction

Protocol Adapter
- Bitcoin Hardware Wallet Interface

Hardware Wallet
- validation + signing logic


### Generic Signing Hurdles
- Ram Size
  - transaction elements usually have to be streamed to the device (worse on a smartcard chip)
  - PSBT is primarily designed for direct processing (large RAM size or mass storage API)
- Signing data processing complexity
  - segwit reduced o(n^2) to o(n)
- Non committment on the full set of UTXO values
  - exploits from this
  - previous UTXOs have to be fully processed by the device to get a reliable fee amount (including segwit UTXOs)

### Boring Bitcoin MultiSignature

Standard Script

Obvious Multisig Issue #1 - identify the public keys
  - public keys have to be validated by all parties safely and securely
  - off-chain protocol agreement to choose

Obvious Multisig Issue #2 - Validate the multi-sig agreement
  - need to review the script coding the agreement, rather than the address

Obvious Multisig Issue #2 - Validate the multi-sig agreement 'in flux'
- consuming input generated chagne addresses, which the signer should validate automatically
- solution described for a subset of possible combinations
  - fixed HD paths (bip 45)
  - public key sorting (bip 67)
  - script structure auto probing (PSBT)
    - auto-probing is already complex for boring multisig script in low RAM environment
    - not scalable for more complex scripts (multisig with A + B or C + D)
    - not scalable for varying change management policies (varying time locked transactions)

These problems have been solved
- human readable script solved by `Miniscript`
  - min.sc
- producing a generic template to derive public keys in this script is solved by 'Output Descriptors'
  - implemented in bitcoin core (bitcoin/doc/descriptors.md)

### Theoretically Sticking thigns together
setup stage
- host sends miniscript olicy
- user validation of the policy on hardware wallet
- wallet sends signed policy

Runtime stage:
- 


On Device Guarantees:
- review miniscript (not the policy) in human readable form
- lock on bitcoin script production according to the extra parameters passed


What's next?
- more detailed description of detached miniscript
- ledger BTC application v2 with Miniscript + Descriptors support
- logic can be adapted to other smartcard chips (e.g. Java Card)
- follow @btchip





