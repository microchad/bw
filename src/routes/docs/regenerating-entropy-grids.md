# Regenerating Entropy Grids

## Deterministic grid regeneration

The Entropy Grid Generator provides the option - when creating your Entropy Grid - to choose Deterministic entropy. By using 128-bits of entropy in the creation of these grids (the same level used when generating 12-word Bitcoin seed backups with 128 dice rolls) we have the ability to simultaneously generate 12 words Regeneration Phrases which allow users to write down a backup to their Entropy Grid in plain text. These Regeneration Phrases are automatically added to the bottom of Deterministic Entropy Grids during generation.

![reg1](/regeneration1.png)

This may seem counter-intuitive to the concept of Border Wallets at first - afterall, we are giving users the ability to memorise seed words, not find new ways of writing new ones down! However, some users may find having the option to make a hand-written or digital copy of 12 grid-regeneration words very useful in some circumstances - for example, if you decide to lodge a copy of an Entropy Grid with a 3rd party for safe-keeping, e.g. a sibling, parent, child, etc. then giving them 12 random words (which look like a Bitcoin seed word backup, but aren't one) instead of a full copy of your Entropy Grid adds an additional level of security. Having 12 words as a representation for an Entropy Grid instead of a PDF file may also open up more opportunities for users to store the keys to their grids.
