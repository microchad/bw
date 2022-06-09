---
previous: Generating Entropy Grids
next: Legacy Planning
---

# Creating a Border Wallet

Time to start making shapes!

> Step 1: Generate your blank Pattern Grid.

![Select Pattern Grid (blank) on the Entropy Grid Generator Tool](/bw_docs_blank_grid_select.png)

<caption>Select Pattern Grid (blank) on the Entropy Grid Generator Tool</caption>

> Step 2: Create your preferred 23-cell 'Pattern' using that blank grid.

If you can, print on paper a copy of the blank grid. Otherwise, you'll likely want to mark-up the digital copy of the PDF on your offline computer using a file editor.

Let's go through an example.

Here I have chosen to honour Bitcoin using a pixelated version of its logo as my Pattern. **The order in which you allocate cells is crucial to remember** when it comes to referencing their corresponding words. In this example, I decide that the cells run down, one column at a time, and from left to right, beginning with cell G21.

![A blank grid with a pattern in the shape of the bitcoin symbol](/bw_docs_blank_grid_patterned.png)

<caption>Your pattern can be anything of your choosing and start anywhere on the grid - it should be sufficiently complex and well-placed to avoid people guessing it if your Entropy Grid is found, but not so complex that it is not memorable to you!</caption>

> Step 3: Generate your preferred Entropy Grid format (Word, Number, Index or Hex).

![The top portion of an unmarked Entropy Grid](/bw_docs_entropy_grid_top_half.png)

<caption>The top portion of an unmarked Entropy Grid</caption>

> Step 4: Transpose your 23-cell pattern from your blank grid to your Entropy Grid.

Did we mention that the order which we reference each word is crucial? Well, it's worth mentioning again. What we can see here is that the 23 seed words from this example, following our order of top-down, left to right, are:

1.) busi 2.) enou.) 3.) neut 4.) casi 5.) matr 6.) life
7.) grit 8.) betw 9.) tren 10.) dash 11.) quar 12.) evok
13.) wash 14.) liza 15.) armo 16.) trum 17.) exac 18.) arte
19.) drip 20.) read 21.) elit 22.) sing 23.) para 24.) [checksum word - which I calculate]

![An Entropy Grid with a bitcoin symbol shaped pattern imposed onto the grid](/bw_docs_entropy_grid_top_half_patterned.png)

<caption>Now we are able to see the 23 seed words that will provide the basis for my Border Wallet: busi enou neut casi matr life grit betw tren dash quar evok wash liza armo trum exac arte drip read elit sing para. We have selected 23 cells - not 24 - and decided on an order of their usage.</caption>

> Step 5: Calculate checksum

We recommend two options for calculating the checksum from your 11 or 23 seed words - the Seed Tool by Bitcoiner.Guide and the SeedSigner.

#### Seed Tool by Bitcoiner.Guide

Bitcoin QnA and SuperPhatArrow's [Seed Tool](https://bitcoiner.guide/seed) provides an excellent option for calculating the checksum word. Download the latest version via their [GitHub repo](https://github.com/BitcoinQnA/seedtool). Like our Entropy Grid Generator, it works offline in an air-gapped browser.

![A screenshot of Seed Tool with the Seed Generation/Input section highlighted](/bw_docs_seed_tool_click_generate.png)

<caption>Click Seed Generation/Input</caption>

![A screenshot from seed tool selecting the Last Word Generator from the BIP39 Tools Menu](/bw_docs_seed_tool_last_word_generator_select.png)

<caption>Scroll down to Select a BIP39 Tool and select Last Word Generator</caption>

Enter each of the four (or three) letter seed words in the correct order into the tool. Make sure you check each word carefully! Seed Tool will automatically suggest the longer version of the word, where applicable, as your enter the first four letters. By the time you reach the 24th entry, Seed Tool has automatically calculated and populated this field for you.

![A screenshot from seed tool using the Last Word Generator](/bw_docs_seed_tool_last_word_generator.png)

To introduce more entropy (randomness) can choose to "Flip the bits" and have it calculate a new checksum - there are 8 possible words that will be shown from a 24 word seed so the checksum could be different if you perform this exercise again, generating a new wallet. This is why you should record/memorise the checksum generated and also make a note of how you generated it in the space provided in the header of your Entropy Grid.

#### SeedSigner

SeedSigner is a great Bitcoin computer (aka 'Hardware Wallet' or 'HWW' or 'Signing Device'). Run as an open-source project with DIY assembly using off-the-shelf components, it provides a cheap, secure, fully air-gapped environment to work in with seed words.

This is the screen that you need to generate the checksum from your seed words.

![Photo of SeedSigner displaying the menu](/bw_docs_seedsigner_menu.png)

If you want to know more about Checksums, [Arman the Parman](https://armantheparman.com/dicev1/) provides his helpful deep-dive on this subject.

> Step 6: Creating a passphrase

We recommend employing a passphrase, but as this adds another thing to remember, then it's your choice whether you want to or not. Also known as a 25th word, as wallet passphrase can significantly increase the security of your wallet. Because this adds a new word to your wallet, it also creates a completely new wallet. So if you do create a passphrase, you will need to ensure you remember it.

> Step 7: Verifying that your wallet works

In order to generate a receive address for your Border Wallet and transfer bitcoin to it, you will need to enter the relevant seed words from your Entropy Grid (your Border Wallet) plus the final checksum word into a Bitcoin computer, e.g. SeedSigner. In doing this, you will have verified that your wallet is valid. Test it by sending a small amount of funds to/from it.

You can also use the [Seed Tool](https://github.com/BitcoinQnA/seedtool) **offline** to check + compare receive addresses, adding another layer of verification before sending funds.

> Step 8: Checking your backups

We recommend performing a full recovery of your Border Wallet on a device of your choosing, **after** you initially set-up your wallet and transfer a small amount of funds to it but **before** transferring large amounts of funds to it. If you have not checked your backups, you do not have any backups!

## Storing your Entropy Grid

Your unmarked Entropy Grid - which essentially serves as a map to buried treasure that only you know the combination lock for - may be kept physically or digitally, depending on your set-up and what you deem most appropriate. The Pattern to unlock the treasury, which you created, will be kept in your head.

However, you may deem it appropriate to keep a copy of your pattern, stored with the same degree of care that you would give a full seed work backup, to serve as either an aide-memoire or to allow someone like your next-of-kin to recover your funds should something happen to you. The choice is yours.

### Legacy planning

Border Wallets can be used as a secure way of transferring funds to children and other relatives without exposing Seed Words to them before you pass away. The next page covers how.
