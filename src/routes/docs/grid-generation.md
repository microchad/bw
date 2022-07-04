# Grid Generation

Border Wallets employ three key components in order to provide users with a reliable means to memorise their Bitcoin wallets:

1. A Pattern
2. An Entropy Grid
3. A checksum

In order to provide users with a practical means for creating all three components, we made a tool - the Entropy Grid Generator (or 'EGG').

The EGG comes as a .html file which opens locally within the user's browser.

The GENERATE tab of the EGG provides users with the ability to create:

- Pattern Grids - for creating and drawing a memorable 'pattern' which the user memorises (1)
- Entropy Grids - for transposing or 'mapping' the pattern onto in order to determine the seed words that will make up the first 11 or 23 words of a user's wallet (2).

The Entropy Grids offer users the ability to work with up to four kinds of grid - a Word Grid (shortened BIP39 seedwords), Number Grids (using their corresponding numbers), Index Grids (the same as Word Grids, but the index is 0 instead of 1) and Hexadecimal Grids (base 16). Most people will want to use Word Grids.

The Entropy Grid Generator uses the Fisher-Yates Shuffle algorithm and the browser’s cryptographically strong pseudo-random number generator seeded with truly random values for generating a random permutation of all BIP-39 seed words.

The option to reproduce Entropy Grids using 12 words as entropy uses Gibson Research Corporation’s Ultra-High Entropy Pseudo-Random Number Generator.

When populating the list of seed words in the Word Grids, only the first four letters of each word are produced in order to save space and time.

![screenshot of the Entropy Grid Generator](/bw-grab2.png)

<caption>The Border Wallets Entropy Grid Generator UI. This runs locally, offline in your browser.</caption>

![A screenshot showing the types of grids available](/bw_docs_blank_grid_select.png)

<caption>You choose from a drop-down menu which grid type to generate</caption>

Both of the types of entropy that users can select are very secure - 128-bit in the case of the Deterministic Grid, and 19,580 for Maximum Entropy Grids. Which one users select will depend on whether they want to have the option to write down - in plain text - a set of words that allows them to restore their Entropy Grid using a backup recovery phrase at a later time (Deterministic Entropy).

![entropy options](/entropy-small.png)

<caption>You have two types of entropy to choose from when generating your grids.</caption>

Once the user has generated their Pattern and their Entropy Grid, and identified which words will form the first 11 or 23 words of their seedphrase, they then need to calculate the final - Checksum - word. The EGG provides a means to do this.
