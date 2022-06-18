---
previous: Words vs Patterns
next: Workflow and Elements
---

# The Solution

Border Wallets provide an easy way to memorise seeds, whether short- or long-term, by using two components - a randomised grid of seed words and a user-generated pattern or cell co-ordinates.

Using our simple tool, users can generate their own entropically-secured, randomised grid of all 2048 BIP-39 compliant seed words, which they generate offline using Entropy Grid Generator, and then apply a sufficiently complex but memorable pattern or set of cell co-ordinates - which only they know - in order to create their wallet.

While our tool is browser-based, it can (and should) be used offline, on an air-gapped PC, Mac or Linux machine - or even using Tails - to run locally in the browser. Users simply download it, transfer it to the machine of their choice and start generating Entropy Grids.

![A grid of words with a pattern on it](/bw_docs_entropy_grid_top_half_patterned.png)

As each unique Entropy Grid contains a complete list of all BIP-39 seed words in randomised format, and the users' patterns exist only in their heads, users may want to store their Entropy Grids either physically or in encrypted files on their devices or on secure online platforms, e.g. BitWarden, Sync, Standard Notes, etc., or email/message them to family/friends).

In order to strengthen their security, users may want to combine their choice of pattern with a sufficiently memorable but hard-to-guess passphrase. In fact, there is no reason why a user cannot generate multiple patterns, and/or multiple Entropy Grids, to create a multi-sig wallet that they can carry in their head.

Hiding your seed words in plain sight - with a sufficiently high difficulty level for brute force attacks - for a given length of time is not out of the question for those running the risk of having physical possessions confiscated or stolen. As the cost of generating Entropy Grids digitally is zero, users can generate dozens or even hundreds of individually numbered grids, storing their preferred grid amongst considerable 'noise'. Imagine a Google Drive, which has 100 unique and individually numbered Border Wallets, and you - the user - being the only person who knows which grid(s) you have used to generate your Border Wallet.

With our Deterministic Grid options, you could introduce a second or multiple-factor grid solution whereby your source Entropy Grid is encoded within other Entropy Grids.

The possibilities are endless.

### Handling Seed Word randomisation

The Entropy Grid Generator uses the [Fisher-Yates Shuffle](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle) algorithm the the browser's [cryptographically strong pseudo-random number generator seeded with truly random values](https://w3c.github.io/webcrypto/#crypto-interface) for generating a random permutation of all BIP-39 seed words. There is also an option to reproduce Entropy Grids using 12 words as entropy to seed [Gibson Research Corporation's Ultra-High Entropy Pseudo-Random Number Generator](https://www.grc.com/otg/uheprng.htm). When populating the list, only the first four letters of each word are produced in order to save space and time.

![Image explaining the algorithm](/Durstenfeld_shuffle.svg)

<caption>Example of shuffling five letters using Durstenfeld's in-place version of the Fisher–Yates shuffle</caption>
