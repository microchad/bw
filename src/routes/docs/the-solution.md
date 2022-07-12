# The Solution

Border Wallets provide a method for memorising seed phrases using two components:

- A randomised grid of all 2048 seed words (an 'Entropy Grid')
- User-generated pattern(s) or cell co-ordinates (a "Pattern)
- The final (checksum) seed word or _number_*.

**Combined, these three factors comprise your Border Wallet.***

Using our offline, browser-based Entropy Grid Generator ('EGG') - users can generate their own entropically-secured, randomised grid of all 2048 BIP-39 compliant seed words, and then apply a memorable pattern or set of cell co-ordinates to it - which only they know - in order to create a wallet.

Whilst the EGG is browser-based, it is designed to work offline on an air-gapped PC, Mac or Linux machine - or even using Tails - and runs locally in the browser. To use it, simply download it, transfer it to the machine of your choice and start generating Entropy Grids.

![A grid of words with a pattern on it](/bw_docs_entropy_grid_top_half_patterned.png)

<caption>An example of a memorable, 23-cell pattern applied to an Entropy Grid to create a Border Wallet. The 24th / final word (the 'checksum') or final word number - the only word that the user memorises - can be calculated natively within the EGG.</caption>

### Evil maid attack difficulty adjustment = up. Memorisation difficulty adjustment = down.

As each unique Entropy Grid contains a complete list of all BIP-39 seed words in randomised format, and the users' patterns exist only in their heads, users will store their Entropy Grid (or its Recovery Phrase) physically or digitally. Because the Entropy Grid comprises all 2048 Bitcoin seed words, any evil maid attacks are faced with an upward difficulty adjustment that is significantly higher than they would be with plain text seed phrase backups.

### Additional security

#### Encryption

For entropy grids stored digitally, e.g. personal computer, USB thumbdrive or secure online cloud storage, the EGG features an option for users to natively encrypt & decrypt their Entropy Grids all within the tool's interface. Once users have created a secure password, they drag + drop their Entropy Grid into the tool for encryption, and then do the same with their encrypted .json file for decryption using the same password.

#### Wallet passphrase

For added security, users can combine their choice of pattern with a sufficiently memorable but hard-to-guess wallet passphrase. In fact, there is no reason why a user cannot generate multiple patterns - or even multiple Entropy Grids (see below) - to create a multi-sig wallet that they can carry in their head.

#### Signal vs Noise

As there is essentially zero cost for generating Entropy Grids, users may choose to generate dozens (or even hundreds) of individually numbered grids, storing their preferred grid amongst considerable 'noise'. Imagine having 100 unique and individually numbered Entropy Grids, and you (the user) being the only person who knows which grid(s) you have used to generate your Border Wallet.

#### Obfuscation & Gridception

Our EGG tool gives users the ability to create Deterministic Entropy Grids, which can be re-generated using a recovery phrase. This feature unlocks the ability to introduce multi-factor grid solutions whereby your source Entropy Grid is encoded within other Entropy Grids; we call this [gridception](https://www.borderwallets.com/docs/gridception) - how deep it goes is up to you :)

## Handling Seed Word randomisation

For Maximum Entropy Grids, the EGG uses the [Fisher-Yates Shuffle](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle) algorithm and the browser's [cryptographically strong pseudo-random number generator seeded with truly random values](https://w3c.github.io/webcrypto/#crypto-interface) for generating a random permutation of all BIP-39 seed words (19,580-bit). The option to reproduce Entropy Grids using 12 words as entropy (128-bit/Deterministic Entropy Grids) uses [Gibson Research Corporation's Ultra-High Entropy Pseudo-Random Number Generator](https://www.grc.com/otg/uheprng.htm).

When populating the list of seed words for Word Grids (one of the four kinds of Entropy Grids the EGG can generate), only the first four letters of each word are produced - in order to save space on each generated grid. The use of only the first four letters of each seed word is an established practice as these letters are unique to each word.

![The letters of the word 'Elvis' are shuffled until it is rearranged to spell 'lives'](/Durstenfeld_shuffle.svg)

<caption>Example of shuffling five letters using Durstenfeld's in-place version of the Fisher–Yates shuffle</caption>
