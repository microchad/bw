---
previous: Words vs Patterns
next: Workflow and Elements
---

# The Solution

Border Wallets provide an easy way to memorise seeds, whether short- or long-term, by using two components - a randomised grid of seed words and a user-generated pattern or cell co-ordinates.

Using our simple tool, users can generate their own entropically-secured, randomised grid of all 2048 BIP-39 compliant seed words, which they generate offline using Entropy Grid Generator, and then apply a sufficiently complex but memorable pattern or set of cell co-ordinates - which only they know - in order to create their wallet.

While our tool is browser-based, it can (and should) be used offline, on an air-gapped PC, Mac or Linux machine - or even using Tails - to run locally in the browser. Users simply download it, transfer it to the machine of their choice and start generating Entropy Grids.

![A grid of words with a pattern on it](/bw_docs_entropy_grid_top_half_patterned.png)

As each unique Entropy Grid contains a complete list of BIP-39 seed words, and the users' pattern exists only in their heads, the user can - if necessary - store their grids either in encrypted files on their devices or on secure online platforms, e.g. BitWarden, Sync, Standard Notes, etc., or email/message them to family/friends, or even (in extreme circumstances) publish them online, e.g. [Twitter](https://twitter.com/).

Whilst we envisage that most Entropy Grids would not be published online (since this presents a potential point of brute-force attacks), the user can - if necessary - choose to employ a sufficiently complex pattern and combine this with a sufficiently memorable but hard-to-guess passphrase to maximise their chances of wallet retrieval. In fact, there is no reason why a user cannot generate multiple patterns, and multiple Entropy Grids, to create a multi-sig wallet that they can carry in their head.

Hiding your seed words in plain sight - with a sufficiently high difficulty level for brute force attacks - for a given length of time is not out of the question for those running the risk of having physical possessions confiscated or stolen. As the cost of generating Entropy Grids digitally is zero, users can generate dozens or even hundreds of individually numbered grids, storing their preferred grid amongst considerable 'noise'.

The possibilities are endless.

### Handling Seed Word randomisation

The Entropy Grid Generator uses the [Fisher-Yates Shuffle](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle) algorithm the the browser's [cryptographically strong pseudo-random number generator seeded with truly random values](https://w3c.github.io/webcrypto/#crypto-interface) for generating a random permutation of all BIP-39 seed words. There is also an option to reproduce Entropy Grids using 12 words as entropy to seed [Gibson Research Corporation's Ultra-High Entropy Pseudo-Random Number Generator](https://www.grc.com/otg/uheprng.htm). When populating the list, only the first four letters of each word are produced in order to save space and time.4
![Image explaining the algorithm](/Durstenfeld_shuffle.svg)

<caption>Example of shuffling five letters using Durstenfeld's in-place version of the Fisher–Yates shuffle</caption>
​
​
