---
previous: Encryption
next: Best Practices
---

# Legacy Planning

## XOR-style seed contruction

Coinkite introduced the concept of SeedXOR which provides a novel way for a 24-word seed phrase to be split into 2 x 24-word seed phrases which each act as their own wallets, but when combined form an entirely new wallet.

![image of seedXOR with cold card](/bw_docs_seedxor.png)

<caption>Learn more about Coinkite's SeedXOR [seedXOR.com](https://seedxor.com/)</caption> ​

We liked the idea, and it can be applied to Border Wallets for legacy planning and handover.

With the Border Wallet approach to Pattern construction, instead of taking a top-down, splitting approach like XOR does, we can adopt a bottom-up, combinatory approach.

### Here's how

#### Step 1

Child A draws (or is given) an 11-word Pattern of their own. You map it onto a master Entropy Grid, and record each word to calculate the checksum. You add a passphrase, creating a wallet, and deposit funds solely for Child A. This is Wallet A. You keep a backup.

> 1. Child A retains Pattern A and the checksum word.
> 2. You retain the master Entropy Grid, and lodge a copy with a solicitor or other trusted 3rd party.

#### Step 2

Child B also draws (or is given) a separate 11-word Pattern of their own. You map this onto the same master Entropy Grid, recording each word to calculate the checksum and depositing funds solely for Child B. This is Wallet B. You keep a backup.

> 1. Child B retains Pattern B and the checksum word.

#### Step 3

You take the 12 words of Chid A's wallet and the first 11 words of Child B's wallet, and calculate another checksum for the combined 23 words. Then you deposit joint funds into this new wallet. This becomes Wallet C. You keep a backup.

> 1. Child A and B both retain a copy of only the checksum for the new wallet, as well as their own Patterns + checksum words.
> 1. Only YOU know both of the Patterns which together make up wallets A, B and C.

#### Step 4

Having recorded the two Patterns for your own records, you retain 1 of 2 copies of the master Entropy Grid, and copy 2 of 2 is lodged with a solicitor or other trusted 3rd party.

#### Step 5

When you pass-away, your children gain access to the master grid, releasing funds for themselves individually and as a pair when they each match their patterns with the grid. Together, they release their combined funds.

> This system can obviously be scaled to account for more children as required.
