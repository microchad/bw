# Creating a Border Wallet

Time to start making shapes!

## Step 1: Generate your blank Pattern Grid.

![Select Pattern Grid (blank) on the Entropy Grid Generator Tool](/bw_docs_blank_grid_select.png)

<caption>Select Pattern Grid (blank) on the Entropy Grid Generator Tool</caption>

## Step 2: Create your preferred 23-cell 'Pattern' using that blank grid.

If you can, print on paper a copy of the blank grid. Otherwise, you'll likely want to mark-up the digital copy of the PDF on your offline computer using a file editor.

Let's go through an example.

Here I have chosen to honour Bitcoin using a pixelated version of its logo as my Pattern. **The order in which you allocate cells is crucial to remember** when it comes to referencing their corresponding words. In this example, I decide that the cells run down, one column at a time, and from left to right, beginning with cell G21.

![A blank grid with a pattern in the shape of the bitcoin symbol](/bw_docs_blank_grid_patterned.png)

<caption>Your pattern can be anything of your choosing and start anywhere on the grid - it should be sufficiently complex and well-placed to avoid people guessing it if your Entropy Grid is found, but not so complex that it is not memorable to you!</caption>

## Step 3: Generate your preferred Entropy Grid format (Word, Number, Index or Hex).

![The top portion of an unmarked Entropy Grid](/bw_docs_entropy_grid_top_half.png)

<caption>The top portion of an unmarked Entropy Grid</caption>

## Step 4: Transpose your 23-cell pattern from your blank grid to your Entropy Grid.

Did we mention that **the order which we reference each word is crucial**? Well, it's worth mentioning again. What we can see here is that the 23 seed words from this example, following our order of top-down, left to right, are:

1.) busi 2.) enou 3.) neut
4.) casi 5.) matr 6.) life
7.) grit 8.) betw 9.) tren
10.) dash 11.) quar 12.) evok
13.) wash 14.) liza 15.) armo
16.) trum 17.) exac 18.) arte
19.) drip 20.) read 21.) elit
21.) elit 22.) sing 23.) para

24.) [This is the checksum (final) word - which I calculate!]

![An Entropy Grid with a bitcoin symbol shaped pattern imposed onto the grid](/bw_docs_entropy_grid_top_half_patterned.png)

<caption>Now we are able to see the 23 seed words that will provide the basis for my Border Wallet: business enough neutral casino matrix life grit between trend dash quarter evoke wash lizard armor trumpet exact artefact drip ready elite sing parade. We have selected 23 cells - not 24 - and decided on an order of their usage.</caption>

## Step 5: Calculate checksum

The EGG includes a feature for calculating the Final (checksum) Word.

Scroll to the Final Word tab in the tool, and enter each of the four (or three) letter seed words in the correct order into the tool. Make sure you check each word carefully! By the time you reach the word, the EGG has automatically calculated and populated this field for you.

<blockquote>The EGG will automatically suggest the longer version of the word, where applicable, as your enter the first four letters of it. **Select this longer word before moving to the next field**</blockquote>

By the time we reach the 24th entry, the final (checksum) word that is calculated from these seed words is 'pair'. In addition to my pattern, I need to memorise this word. However, I could choose to also remember its corresponding Final Word 'Number'.

![Screenshot of Final Word Calculator](/finalword.png)

<caption>The Final Word tab allows you to calculate the checksum. It also has a Final Word Number feature.</caption>

### Final Word 'Number'

In order to help make the memorisation of the final word even easier, the EGG includes a unique Final Word Number feature. This means that instead of needing to remember the word itself (in my case above, this word is "pair"), I can just remember a number (in this case "5"). I could even write down this number on my Entropy Grid itself or somewhere else - since on its own, it is meaningless and provides no clues about my final word without the other words.

Users can, if necessary, use the scroll button at the end of the Final Word Number field to change the number to something more meaningful to them, but this also changes the final word itself. Therefore if you do change the number, the new checksum shown must be used to set-up your Border Wallet. We don't advise users change the number (since it too is generated with entropy by the tool), but you can do if you want to.

![Screenshot of Final Word Calculator](/finalwordnumber4.png)
![Screenshot of Final Word Calculator](/finalwordnumber3.png)
![Screenshot of Final Word Calculator](/finalwordnumber2.png)

<caption>The Final Word Calculation feature allows you to remember a number instead of the checksum word itself. You can use this same part of the tool to remind yourself of the checksum word to apply when creating or restoring your Border Wallet.</caption>

If you want to know more about Checksums, [Arman the Parman](https://armantheparman.com/dicev1/) provides a helpful deep-dive on this subject.

## Step 6: Creating a passphrase

We **highly recommend employing a passphrase**, but as this adds another thing to remember, then it's your choice whether you want to or not. Also known as a 25th word, as wallet passphrase can significantly increase the security of your wallet. Because this adds a new word to your wallet, it also creates a completely new wallet. So if you do create a passphrase, you will need to ensure you remember it.

## Step 7: Verifying that your wallet works

In order to generate a receive address for your Border Wallet and transfer bitcoin to it, you will need to enter the relevant seed words from your Entropy Grid (your Border Wallet) plus the final checksum word into a Bitcoin hardware wallet. In doing this, you will have verified that your wallet is valid. Test it by sending a small amount of funds to and from it.

You can also use the [Seed Tool](https://github.com/BitcoinQnA/seedtool) **offline** to check and compare receive addresses, adding another layer of verification before sending funds.

## Step 8: Checking your backups

We recommend performing a full recovery of your Border Wallet on a device of your choosing, **after** you initially set-up your wallet and transfer a small amount of funds to it but **before** transferring large amounts of funds to it. If you have not checked your backups, you do not have any backups!

## Storing your Entropy Grid

Your unmarked Entropy Grid - which essentially serves as a map to buried treasure that only you know the combination lock for - may be kept physically or digitally, depending on your set-up and what you deem most appropriate. The Pattern to unlock the treasury, which you created, will be kept in your head.

However, you may deem it appropriate to keep a copy of your pattern, stored with the same degree of care that you would give a full seed work backup, to serve as either an aide-memoire or to allow someone like your next-of-kin to recover your funds should something happen to you. The choice is yours.

If you choose to store digital copies of these, you might consider encrypting the files. The Entropy Grid Generator contains a tool for encrypting files which we explain [here](https://borderwallets.com/docs/encryption-and-decryption).
