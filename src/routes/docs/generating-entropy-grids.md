---
previous: Download the Entropy Grid Generator
next: Creating a Border Wallet
pageNo: 6
---

# Generating Entropy Grids

**Please read the advisory notes below carefully**, and also the pages that follow about creating Border Wallets.

After downloading the Entropy Grid Generator (filename: borderwallets.html) and transferring it to your air-gapped machine, you can launch it. You will see this open locally within your browser:

![screenshot of the Entropy Grid Generator](/bw-grab2.png)

<caption>The Border Wallets Entropy Grid Generator UI. This runs locally, offline in your browser.</caption>

The Entropy Grid Generator allows users to generate five types of grids - one blank, and four types of Entropy Grid.

1. A Pattern Grid (applicable for all users).
   This provides you with a blank grid to create your own patterns or to mark your preferred cell co-ordinates. This is the first grid you should download and create, so as not to be influenced by the words outputted (word bias)

2. A Word Grid (recommended for 99% of users).
   Word Grids employ only the first four letters of each seed word. This allows us to produce a randomised grid of all 2048 BIP-39 compatible words as a 2-page PDF. If you are not familiar with how BIP-39 works and why only the first four letters of a seed word are required for wallet generation and recovery, [read this](https://www.blockplate.com/pages/first-4-letters-of-a-bip39-mnemonic-seed-phrase). You can review a full list of seed words and their respective first four letters [here](https://docs.google.com/spreadsheets/d/1MlQJ8sAQgL_bleI7L0eolrpqsthn9Nxhb4tWXi_Pvhw/edit?usp=sharing).

3. A Number Grid (some users may prefer to use this).
   This gives the option to work with the numbers associated with BIP39 seed words where the index is 1 (0001-2048), e.g. Abandon = 0001, up to 2048.

4. An Index Grid (a very small number of users may prefer to use this).
   This gives the option to work with the numbers associated with BIP39 seed words where the index is 0, e.g. Abandon = 0000, up to 2047.

5. A Hex Grid (a tiny number of technical users may choose to use this).
   This gives the option to work with hexadecimal alphanumeric characters (base16).

![A screenshot showing the types of grids available](/bw_docs_blank_grid_select.png)

<caption>You choose from a drop-down menu which grid type to generate</caption>

Most users will opt for Word Grids, which produces the first four letters of each BIP39 seed word in a randomised order using the Fisher-Yates Shuffle algorithm with strong randomness running locally in your browser.

![entropy options](/entropy-small.png)

<caption>You have two types of entropy to choose from when generating your grids.</caption>

We offer users the ability to employ two types of entropy when generating their Entropy Grids - 128-bit and 19580-bit:

    - The 128-bit option provides users with *deterministic* entropy grid reproducibility - i.e. the ability to backup grids in plain text as 12 words and regenerate later them using the Entropy Grid Generator. Whilst this may seem counter-intuitive to the concept of Border Wallets, grid reproducability using words that can be written in plain text may serve an important role for some users, e.g. for backup, grid-distribution, or decoy purposes, etc.
    - The 19580-bit option provides users with the *maximum* level of entropy. Because of the immense randomness* of these grids, regeneration using backup words is not possible. These grids must therefore be saved and stored safely, physically or digitally, as there is no way to regenerate them later using backup words.

_*2048! (2048 factorial) - a number so large that it is really hard to comprehend: 1.67 &times; 10<sup>5894</sup>_

When you hit "GENERATE GRID", your grid - formatted as a 2-page PDF - will be sent to your downloads folder or a new tab in your browser.

---

## Exploring the Grids

Let's examine this in a little more detail before we move on.

### Pattern Grids

Blank **Pattern Grids** let you plan which cells you will use to generate your Border Wallet - and then map them out. You can experiment with different starting points, end points, shapes, co-ordinates, etc. before you commit the Pattern to your Entropy Grid. Remember, you have 2 sides you can choose from - you might choose to use one side, or both - splitting your pattern or having two or more across your 23-preferred cells (if generating a 24-word Border Wallet).

![2 sheets of A4 paper printed with a blank grid on each](/bw_docs_two_blank_grids.png)

<caption>The Blank Pattern Grid gives you 16 columns (marked A-P) x 128 rows, across 2 sides of A4, to choose from when devising your Border Wallet pattern or co-ordinates. That's 2048 cells to choose from</caption>

Once you have settled on a sufficiently complex, well-placed and memorable shape or set of co-ordinates (which we call your Pattern), you will then need to transpose it onto your choice Entropy Grids (you choose from the Word, Number, Index or Hex Grid based on your comfort/familiarity with each) in order to start generating your Border Wallet. If you are new to this, choose the Word Grid.

### Entropy Grids

#### The Word Grid

![grid-word](/grid-word.png)

<caption>An example of the top 21 rows of a randomised Word Grid. Word Grids reproduce all 2048 seed words from the BIP39 list, randomised using the Fisher-Yates Shuffle algorithm</caption>

The vast majority of users will choose to use Word Grids as opposed to the other kinds. Only the first 4 letters of each word are rendered as that is all that's required for seed phrase generation (some words have only 3 letters, e.g. fit, six, lab). By using these truncated words, with a smaller character set, gives us the ability to fit all 2048 words onto just two readable pages.

#### The Number and Index Grids

![grid-number](/grid-number.png)

<caption>An excerpt from the top 21 rows of a randomised Number Grid</caption>

Number and Index Grids are virtually identical to each other when not randomised, with one key difference -the Number Grid uses an index of 0001 (attributable to the seed word 'Abandon') whereas the Index Grid uses an index of 0000 (also for 'Abandon').

> Note that if you choose to generate both a Number and Index Grid together (not recommended!), the outputted files will be totally different.

#### The Hex Grid

![grid-hex](/grid-hex.png)

<caption>An excerpt from the top 21 rows of a randomised Hex Grid. Make sense? If not, don't use this one! :)</caption>

Hex Grids draw from the corresponding alphanumeric hexadecimal character set, with base 16. There are some but relatively few people who would want to use this - those that do will need no further expansion here on how they are used.

> The four types of Entropy Grids that the Entropy Grid Generator produces do NOT co-respond to each other. They will ALL be different to one another, and to each successive one that is generated. They should therefore be treated as unique Entropy Grids. We recommend choosing to standardise on one type of Entropy Grid (e.g. Word Grid) and sticking with it.
>
> **If you do wish to print multiple types of the exact same grid**, for example, one hex and one words but both with the same entropy, you should select a deterministic entropy grid and use the generated seed from that grid to reproduce your grid in different types.

OK. That's the grids covered; let's move to the next section to start creating your Border Wallet.
