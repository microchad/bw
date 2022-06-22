---
previous: Words vs Patterns
next: Workflow and Elements
pageNo: 3
---

# The Solution

Border Wallets provides a method for memorising seed phrases using two components:

- A randomised grid of all 2048 seed words (an 'Entropy Grid').
- User-generated pattern(s) or cell co-ordinates.

Using our offline, browser-based tool (the 'Entropy Grid Generator' or EGG) - users can generate their own entropically-secured, randomised grid of all 2048 BIP-39 compliant seed words, and then apply a memorable pattern or set of cell co-ordinates to it - which only they know - in order to create a wallet.

Whilst our EGG tool is browser-based, it is designed to work offline on an air-gapped PC, Mac or Linux machine - or even using Tails - and runs locally in the user's browser. To use, simply download it, transfer it to the machine of your choice and start generating Entropy Grids.

![A grid of words with a pattern on it](/bw_docs_entropy_grid_top_half_patterned.png)

As each unique Entropy Grid contains a complete list of all BIP-39 seed words in randomised format, and the users' patterns exist only in their heads, users need to store their Entropy Grid (or its Recovery Phrase) physically or digitally on their devices or secure online platforms, e.g. BitWarden, Sync, Standard Notes, etc., or email/message them to a trusted 3rd party). Our EGG also features native encryption and decryption capabilities. 

For additional security, users may want to combine their choice of pattern with a sufficiently memorable but hard-to-guess passphrase. In fact, there is no reason why a user cannot generate multiple patterns - or even multiple Entropy Grids - to create a multi-sig wallet that they can carry in their head.

As the cost of generating Entropy Grids digitally is zero, users can generate dozens or even hundreds of individually numbered grids, storing their preferred grid amongst considerable 'noise'. Imagine a secure online storage folder, which has 100 unique and individually numbered Entropy Grids, and you (the user) being the only person who knows which grid(s) you have used to generate your Border Wallet.

With that said, we strongly recommend keeping your grids secret and undisclosed wherever possible.

We also provide users with the ability to create Deterministic Entropy Grids, which can be re-generated using a recovery phrase. This gives rise to the ability to introduce multi-factor grid solutions whereby your source Entropy Grid is encoded within other Entropy Grids - like a form of 'gridception' (h/t @superphatarrow).

The possibilities are endless.

### Handling Seed Word randomisation

The Entropy Grid Generator uses the [Fisher-Yates Shuffle](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle) algorithm and the browser's [cryptographically strong pseudo-random number generator seeded with truly random values](https://w3c.github.io/webcrypto/#crypto-interface) for generating a random permutation of all BIP-39 seed words.

The option to reproduce Entropy Grids using 12 words as entropy uses [Gibson Research Corporation's Ultra-High Entropy Pseudo-Random Number Generator](https://www.grc.com/otg/uheprng.htm).

When populating the list of seed words, only the first four letters of each word are produced in order to save space and time.

![The letters of the word 'Elvis' are shuffled until it is rearranged to spell 'lives'](/Durstenfeld_shuffle.svg)

<caption>Example of shuffling five letters using Durstenfeld's in-place version of the Fisher–Yates shuffle</caption> 
