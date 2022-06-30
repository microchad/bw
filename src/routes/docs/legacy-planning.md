# Legacy Planning

Here are a couple of examples of ways that you can leave wealth to your descendants. These are by no means the only ways and are just provided to illustrate some creative methods for accomplishing this. Once you grasp all the possibilities, you can taylor-make a solution that fits your circumstances best.

> **WARNING:** The more complicated your solution, the more chance it has of failing so when making legacy plans, you should not only think adversarially about the way your wealth can be stolen, but also how they could be lost because your loved ones are unable to untangle the complications you have protected them with.
>
> **Always ensure there are safe, but detailed instructions for unlocking the finances!**

## XOR-style Seed Construction

Coinkite introduced the concept of SeedXOR which provides a novel way for a 24-word seed phrase to be split into 2 x 24-word seed phrases which each act as their own wallets, but when combined form an entirely new wallet.

![seedXOR with cold card](/bw_docs_seedxor.png)

<caption>Learn more about Coinkite's <a href="https://seedxor.com/">seedXOR.com</a></caption> ​

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

## Dead Man's Switch

#### What is FinalMessage?

[Final Message](https://finalmessage.io) is an implementation of a ‘dead man’s switch’ that uses bitcoin payments as the trigger mechanism with an emphasis on privacy and security. Final message is made for and run by reputable Bitcoiners, including [Matt Odell](https://twitter.com/ODELL).

#### What is a dead man’s switch?

Dead man’s switches are designed to require positive action or they will automatically deploy. They are ideal for situations where you are worried about unforeseen death, kidnapping, or memory loss. If you don’t engage the trigger for a certain amount of time, the switch automatically sends the desired message.

In the case of Final Message, an encrypted message will be emailed to an email address you provide.

#### How can this be coupled with Border Wallets?

Here a few examples of combining these two tools. These are just ideas designed to spark your imagination into coming up with the right method for your situation.

- Leave a Pattern Grid in your Last Will and Testament and encrypt the instructions and Entropy Grid Regeneration Phrase with Final Message to be emailed to your beneficiaries. One pattern can work on multiple Entropy Grids so you can leave different Entropy Grids for different people or different Pattern Grids for different people that all work off of the same Entropy Grid. The decryption passphrase can be left in your will.

- Provide loved ones with encrypted thumb drives (always duplicate them for redundancy due to [bit rot](https://en.wikipedia.org/wiki/Data_degradation)) containing instructions and/or grids. The passwords to decrypt the drives can be sent via Final Message.

- Encrypt your Entropy Grid and store the encrypted file in the cloud. Include a link to the Encrypted Entropy Grid, the passphrase to decrypt the grid in your Final Message. The Pattern Grid can be included in your Last Will and Testament along with the passphrase to decrypt the Final Message.

## Tips for Making Your Plan

- Think about what is right for you and your family, their level of technical ability and your threat model.
- Think about all the ways it can go wrong and how you can mitigate against it.
- Keep it as simple as possible without losing security.
- Split parts between people and services to prevent points of failure. Have secure redundancy in case those people are not around.
- Pattern Grids in Border Wallets are patterns for the simple reason that people are better at remembering patterns but in the legacy case, a pattern can be just a list of cells e.g. A5, B6, ... etc since no one needs to remember them in this use case.

The next two sections will contain more to helps you make good decisions.
