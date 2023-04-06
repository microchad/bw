# Best Practices

Here are some tips for ensuring you maximise the security of your Border Wallet. We will consider general tips and then tips specifically for two user modes - ⚔️ FIGHT and 🏃‍♂️ FLIGHT.

> General tips

- Download and use the Entropy Grid Generator on an air-gapped, offline computer.
- Number & date each Entropy Grid you generate. This will help you later if you generate multiple grids. Spaces are provided in the headers for making notes.
- Devise a pattern or mark cell co-ordinates for your Border Wallet on the blank Pattern Grid before you commit it to your Entropy Grid - this avoids word bias.
- Do not use the same cell more than once.
- The order in which you select cells offers an additional layer of security and attack-protection. For 11 cell patterns, there are 39 million possible combinations for the order; for 23 cell patterns, there are 258 quintillion order combinations.
- The more Entropy Grids you generate, the harder it will be for an attacker to know which one(s) you have used. More grids = more noise; more noise = more work needed to attack. You must remember which ones you have used, though!
- You should be the only one who knows the Pattern that provides the correct counterpart to your Entropy Grid, unless you trust any 3rd parties in the same way you would trust them with your private keys.
- Use a passphrase ('25th word') when creating your Border Wallet.
- Use the Pattern Grid to mark 11 or 23 cells, which will correspond to 11 or 23 words from your Entropy Grid. You can use the Final Word tab in the EGG tool to calculate the Final Word (Checksum).
- Verify that your Border Wallet works - generate a receive address and send a small amount of bitcoin to it.
- Check that your backups work by performing a full restore before transferring larger amounts to it.
- The more unique Entropy Grids you have and keep together, the more difficult it will be for an attacker to successfully determine which one is used and for your Border Wallet to be compromised.
- The more complex your Pattern, the more difficult it is to attack - but also the more difficult it is to remember.
- Use secure, encrypted services if storing your Entropy Grids online, e.g. the EGG's native encryption feature.
- Use tamper-evidencing tools (e.g. bags) if storing your Entropy Grids physically.
- Don't keep any printed versions of your Pattern Grid in the same place as your Entropy Grid - in case they are both found.

> Think Outside the Box

- You may find it useful to create multiple wallets using the same Pattern, transposed across multiple grids, in order to provide you with a "Canary in the Coal Mine" early warning system of an element of your security being compromised.
- You might find it useful to introduce your our markings, colourings, etc. to your Entropy Grids to serve as either decoys or tips that only you would know the relevance of. What may appear nonsensical to a nosy maid may be revelatory to you and, indeed, what may be seem like a clue to a nosy maid may be a deliberate decoy left by you. Be creative.
- You could use several patterns (or apply the same pattern across several Entropy Grids) to generate multi-sig wallets. This would dramatically increase the security of your Border Wallet.
- Rotating your Pattern by 90, 180 or 270 degrees could add some further entropy to your pattern.

> ⚔️ FIGHT MODE TIPS

These tips are aimed at users whose physical security is relatively strong. Following the General Tips above, you may wish to consider the following:

- Keep your Entropy Grids secret for as long as practically possible - if you don't need to share it with someone - e.g. legacy handover, etc. then don't.
- Ideally, treat your Entropy Grid - and especially any corresponding patterns that you generate - with the same care and OpSec attentiveness as you would treat a full seed phrase backup.

> 🏃‍♂️ FLIGHT MODE TIPS

These tips are aimed at users whose physical/accommodation security is weak, who live in a political hot zone or who are often on the move with no permanent fixed abode. Following the General Tips above, you may wish to consider the following:

- When considering where to store your Entropy Grids, aim to strike an acceptable balance between a place(s) that minimises its attack surface and accessibility. Make it both securely stored but retrievable in a hurry.
- Consider how you will be able to successfully access your Entropy Grid and recreate your Border Wallet when you need it.
- Prepare for the worst (e.g. confiscation, theft, fire).
- Consider whether minimising the amount of time your Entropy Grid is stored in any one place would reduce its chances of being discovered.
- If you want to keep a physical copy of your Entropy Grid with you, consider making it available to yourself elsewhere, e.g. via digital storage, in case you lose your physical copy. Encrypted storage is the most secure method for storing your grids, but you must remember the passwords to access them.

## Factors which increase the likelihood of your Entropy Grid being found and/or attacked

By considering these key elements, you can implement your own difficulty adjustment for a attacker.

![four simple line graphs](/bw_docs_five_graphs.png)

<caption>Variables which impact the risks of your Memory Map being exposed to an attacker</caption>
