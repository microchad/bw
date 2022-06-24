---
previous: The Solution
next: Download the Entropy Grid Generator
pageNo: 4
---

# Summary: Workflow & Elements

Here is a quick workflow summary of the Border Wallet creation process. We will talk you through each step of this over the next few pages.

![Flowchart explaining the Border Wallets process](/bw_process_flowchart.png)

The key elements that you will be working with, produced in the order that you will work with them, are:

1. Pattern Grid - our tool produces a blank version, which you will use to create your 23-cell patterns or mark your preferred co-ordinates
1. Entropy Grid - with seed words, number, indices or hex characters, randomised by our Fisher-Yates shuffle algorithm. Once your Pattern Grid is completed, you will transpose it to your Entropy Grid.

Your Border Wallet is produced when you combine 1+2, plus a 24th 'checksum' word (instructions are included later) and, if you want to use one, a passphrase.

![summary1](/summary1.svg)

<caption>You work with two grids - a blank Pattern grid and an unmarked Entropy Grid.</caption>

![summary2](/summary2.svg)

<caption>The Border Wallet is complete once you have memorised your Pattern + checksum, and safely stored your Unmarked Entropy Grid</caption>

Once you have completed these steps, and memorised your pattern or cell co-ordinates, you will retain the unmarked Entropy Grid, and either dispose of the Pattern Grid or treat it with the same high-degree of OpSec that you would a full, hand-written seed word backup. The same applies for the marked-up Entropy Grid - this literally contains the full key combination to your stack, so you must choose to either destroy it or treat it with the utmost security care.

The whole point of the Border Wallet concept is to be able to memorise your Pattern and to carry this pattern in your head. Therefore the only remaining token of your exercise should be the unmarked Entropy Grid - which, when combined with the Pattern allows you to restore your wallet when necessary.

![summary3](/summary3.svg)

<caption>Your final Border Wallet will comprise (1) a securely stored/retained unmarked Entropy Grid, (2) your memorised pattern, (3) the checksum (and your optional passphrase if used). Any marked-up Entropy Grids should therefore be destroyed.</caption>

Make sense? Let's walk through it one step at a time, beginning with generating Entropy Grids.
