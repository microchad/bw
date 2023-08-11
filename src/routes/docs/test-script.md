# Border Wallets Test Script

## Objective

To ensure that users are able to create, save and recover Border Wallets and Entropy Grids using a 3rd-party integration of the Border Wallets concept.

## Test Environment

The test should be conducted on the platforms and versions that are supported by the developer of the app that is integrating Border Wallets.

1. Launch the Application

- [ ]  Launch app and check Border Wallets feature is enabled
- [ ] Navigate to Border Wallets feature and check the following are accessible
	- [ ] Generate blank Pattern Grid
	- [ ] Generate new Entropy Grid
	- [ ] Recover existing Entropy Grid via Recovery Phrase
	- [ ] Recover existing Entropy Grid via Import Entropy Grid / Load PDF

2. Generate Blank Pattern Grid

- [ ] Generates Columns A to P, listed correctly from left to right
- [ ] Generates Rows 1 to 128, listed chronologically from 1 on the first row to 128 on the last, top down

3. Create a Pattern

- [ ] Provides instructions in Dialogue Box to "Create your Border Wallets Pattern, by selecting either 11 or 23 cells in the grid. Note that the order of selection is important"
- [ ] Warns users that they must select cells individually - and NOT by "dragging the cursor/trying to select multiple cells in one click"
- [ ] Allows user to select any combination of 11 or 23 cells to create pattern in Blank Pattern Grid
- [ ] Allows users to select any combination of 11 or 23 cells to create pattern in Entropy Grid
- [ ] Does not allow user to select more than 23 cells, or prevents user from being able to proceed if cell count is exceeded
- [ ] Restarts cell selection if user tries to Select the same cell twice or Cancels the cell selected & unselected to reset the numbering, ignoring the user state change
- [ ] Restarts/resumes cell selection if user tries to Deselect cells
- [ ] Restarts cell selection if user tries to drag cursor over more than one cell or prevents cell drag/simultaneously selecting multiple cells
- [ ] Allows user to Clear Selection and restart pattern entry from scratch
- [ ] Records which cells the user selects and in exactly the correct order
- [ ] Prevents user from selecting the same cell twice (anti-pattern)

4. Generate Entropy Grid

- [ ] Generates Columns A to P, listed correctly from left to right
- [ ] Generates Rows 1 to 128, listed chronologically from 1 on the first row to 128 on the last, top down
- [ ] Generates new, randomised entropy grid of all 2048 BIP39 seed words
- [ ] Generates grid as PDF
- [ ] Prompts user to Save Grid PDF
- [ ] Prompts user to Save Grid Recovery Seed Phrase after they have Generated New Grid
- [ ] Warns users if Entropy Grid has not been saved by the user with warning that funds may be lost
- [ ] Automatically saves Entropy Grid, naming it with the same name that the User gave to their wallet in previous dialogues

5. Import Entropy Grid

- [ ] Allows user to Load Grid PDF
- [ ] Allows user to Enter Grid Recovery Phrase
- [ ] Faithfully imports or regenerates a copy of the original grid

6. Create Border Wallet

- [ ] Transposes user's 11 or 23 cell selection onto the generated grid
- [ ] Highlights the 11 or 23 selected cells so that it is clear which ones will construct their wallet
- [ ] Imports the user's 11 or 23 selected cells into a wallet generation field in the correct order in which the cells were selected
- [ ] Prompts user to Enter or Select a Checksum (e.g. from a drop-down menu)
- [ ] Prompts user to Enter or Select a Checksum or Final Word Number
- [ ] Prompts user to Create or Enter Passphrase, if desired

7. Create Wallet File

- [ ] Prompts user to Create Keystore
- [ ] Shows Derivation Path
- [ ] Prompts user to Import Keystore
- [ ] Shows Settings
	- [ ] Policy Type, e.g. Single Signature
	- [ ] Script Type, e.g. Native Segwit
- [ ]  Shows Script Policy
	- [ ] Descriptor - e.g. wpkh (BIP39)
- [ ] Shows Keystores
- [ ] Shows option to review Seed Phrase
- [ ] Shows correct seed which matches Entropy Grid pattern selection
- [ ] Provides option to add Label
- [ ] Shows Master Fingerprint
- [ ] Shows Derivation
- [ ] Shows xpub/zpub
- [ ] Prompts user to Create or Enter Password, if desired

- End of Test -


Test Result

- [ ] Pass
- [ ] Fail
