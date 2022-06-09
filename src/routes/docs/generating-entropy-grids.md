---
previous: Download the Entropy Grid Generator
next: Creating a Border Wallet
---

# Generating Entropy Grids

After downloading the Entropy Grid Generator, please read these advisory notes carefully, and also the pages that follow about creating Border Wallets.

Now that the Entropy Grid Generator ZIP file is on your air-gapped machine, unzip it and launch the 'borderwallets.html' file.

![image of a filesystem list of files with borderwallets.html highlighted](/bw_docs_html_file_highlighted.png)

You will see this open locally within your browser:

![image of the main screen of the Entropy Grid Generator](/bw-grab.png)
<caption>The Border Wallets Entropy Grid Generator UI. This runs locally, offline in your browser.</caption>

The Entropy Grid Generator allows users to generate five types of Entropy Grids - one blank, and four other randomly populated grids.

1. A Pattern Grid (recommended for all users).
This provides you with a blank grid to create your own patterns or to mark your preferred cell co-ordinates. This is the first grid you should download and create, so as not to be influenced by the words outputted (word bias)

2. A Word Grid (recommended for 99% of users).
Word Grids employ only the first four letters of each seed word. This allows us to produce a randomised grid of all 2048 BIP-39 compatible words as a 2-page PDF. If you are not familiar with how BIP-39 works and why only the first four letters of a seed word are required for wallet generation and recovery, [read this](https://www.blockplate.com/pages/first-4-letters-of-a-bip39-mnemonic-seed-phrase). You can review a full list of seed words and their respective first four letters [here](https://mtc-2.gitbook.io/borderwallets.com/bip39-seed-words).

3. A Number Grid (some users may prefer to use this).
This gives the option to work with the numbers associated with BIP39 seed words where the index is 1 (0001-2048), e.g. Abandon = 0001, up to 2048.

4. An Index Grid (a very small number of users may prefer to use this).
This gives the option to work with the numbers associated with BIP39 seed words where the index is 0, e.g. Abandon = 0000, up to 2047.

5. A Hex Grid (a tiny number of technical users may choose to use this).
This gives the option to work with hexadecimal alphanumeric characters (base16).

![A screenshot showing the types of grids available](/bw_docs_blank_grid_select.png)
<caption>You choose from a drop-down menu which grid type to generate</caption>

Most users will generate only two grids (the Pattern Grid + the Word Grid).


---

## Exploring the Grids

Let's examine this in a little more detail before we move on.

### Pattern Grids

Blank **Pattern Grids** let you plan which cells you will use to generate your Border Wallet - and then map them out. You can experiment with different starting points, end points, shapes, co-ordinates, etc. before you commit the Pattern to your Entropy Grid. Remember, you have 2 sides you can choose from - you might choose to use one side, or both - splitting your pattern or having two or more across your 23-preferred cells (if generating a 24-word Border Wallet).

![image of 2 sheets of A4 paper printed with a blank grid on each](/bw_docs_two_blank_grids.png)

<caption>The Blank Pattern Grid gives you 16 columns (marked A-P) x 128 rows, across 2 sides of A4, to choose from when devising your Border Wallet pattern or co-ordinates. That's 2048 cells to choose from</caption>

Once you have settled on a sufficiently complex, well-placed and memorable shape or set of co-ordinates (which we call your Pattern), you will then need to transpose it onto one of the four Entropy Grids (choose from the Word, Number, Index or Hex Grid based on your comfort/familiarity with each) in order to start generating your Border Wallet.

### Entropy Grids

#### The Word Grid

![grid-word](/grid-word.png)
<caption>An example of the top 21 rows of a randomised Word Grid. Word Grids reproduce all 2048 seed words from the BIP39 list, randomised using the Fisher-Yates Shuffle algorithm</caption>

The vast majority of users will choose to use Word Grids as opposed to the other kinds. Only the first 4 letters of each word are rendered as that is all that's required for seed phrase generation (some words have only 3 letters, e.g. fit, six, lab). By using these truncated words, with a smaller character set, gives us the ability to fit all 2048 words onto just two readable pages.

#### The Number and Index Grids

![grid-number](/grid-number.png)
<caption>An excerpt from the top 21 rows of a randomised Number Grid</caption>

Number and Index Grids are virtually identical to each other when not randomised, with one key difference -the Number Grid uses an index of 0001 (attributable to the seed word 'Abandon') whereas the Index Grid uses an index of 0000 (also for 'Abandon').

Note that if you choose to generate both a Number and Index Grid together (not recommended!), the outputted files will be totally different.

#### The Hex Grid

![grid-hex](/grid-hex.png)
<caption>An excerpt from the top 21 rows of a randomised Hex Grid. Make sense? If not, don't use this one! :)</caption>

Hex Grids draw from the corresponding alphanumeric hexadecimal character set, with base 16. There are some but relatively few people who would want to use this - those that do will need no further expansion here on how they are used.

> The four types of Entropy Grids that the Entropy Grid Generator produces do NOT co-respond to each other. They will ALL be different to one another, and to each successive one that is generated. They should therefore be treated as unique Entropy Grids. We recommend choosing to standardise on one type of Entropy Grid and sticking with it.

OK. That's the grids covered; let's move to the next section to start creating your Border Wallet.
