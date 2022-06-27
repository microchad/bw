---
previous: Workflow and Elements
next: Generating Entropy Grids
pageNo: 5
---

# Download the Entropy Grid Generator

Let's dive in!

Download the latest files below or check out the older [releases](https://github.com/microchad/borderwallets/releases)

- **Border Wallets Entropy Grid Generator:** [borderwallets.html](https://github.com/microchad/borderwallets/releases/latest/download/borderwallets.html)
- **Hash File:** [borderwallets.txt](https://github.com/microchad/borderwallets/releases/latest/download/borderwallets.txt)
- **Signature File:** [borderwallets.txt.asc](https://github.com/microchad/borderwallets/releases/latest/download/borderwallets.txt.asc)

# Verifying the Release

_While the following steps may seem intimidating to people that are not used to working in the command line, they are extremely important for your security and not as daunting if you just take them one step at a time._

For all Bitcoin wallets, it’s a particularly important security step to verify the release. This is done to ensure the Entropy Grid Generator file you download has not been compromised. In order to do so, you’ll need to have gpg or gpg2 installed on your system (see here for [OSX](https://gpgtools.org/) or [Windows](https://www.gpg4win.org/), on Linux it’s preinstalled). Once you’ve installed gpg, you’ll need to use the command line. You can do this by opening `Terminal.app` in OSX, or `Start > Run > cmd` in Windows.

## Verify the Signature

First, import the keys that have signed this release (if you haven’t done so already):

```
curl https://borderwallets.com/pgp.txt -L | gpg --import
```

Once you have the required PGP keys, you can verify the release. Download borderwallets.txt and borderwallets.txt.asc from the links above to the same directory (for example, your Downloads directory). In your terminal, change directory (`cd`) to the one where the downloaded files are, for example:

```
cd Downloads
```

Uppercase & lowercase lettering must be honoured, so if your Downloads folder beings with a small 'd', use that.

Once you are in the correct directory, you can verify the signatures are genuine using the `gpg --verify borderwallets.txt.asc` command. The output should be similar to what follows for a successful verification:

```
gpg --verify borderwallets.txt.asc

gpg: assuming signed data in 'borderwallets.txt'
gpg: Signature made Sun 19 Jun 2022 01:05:34 UTC
gpg:                using RSA key 6067FDB146D964B9BF5731FF876821EC200DC4DC
gpg:                issuer "superphatarrow@pm.me"
gpg: Good signature from "superphatarrow <superphatarrow@pm.me>" [ultimate]
```

Note that you may get a message similar to the following:

```
gpg --verify borderwallets.txt.asc

gpg: assuming signed data in 'borderwallets.txt'
gpg: Signature made Sun 19 Jun 2022 01:05:34 UTC
gpg:                using RSA key 6067FDB146D964B9BF5731FF876821EC200DC4DC
gpg:                issuer "superphatarrow@pm.me"
gpg: Good signature from "superphatarrow <superphatarrow@pm.me>" [ultimate]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
```

This simply means that you have not explicitly marked the public key as trusted in your own instance of GPG. In this case it is good practice to check the key against other sources, for example https://pgp.mit.edu/pks/lookup?search=superphatarrow%40pm.me&op=index (click on the link of the fingerprint to see the full public key). You can read more about validating keys in the [GnuPG Privacy Handbook](https://www.gnupg.org/gph/en/manual/x334.html).

## Verify the Hash of the File

You have now verified the signature of the hash file, which ensures integrity and authenticity of the hash file - not the Entropy Grid Generator itself! Next, depending on your operating system, you must re-compute the sha256 hash of the Entropy Grid Generator with `shasum -a 256 <filename>`. First, download the installation for your operating system (if you haven’t done so already). Then follow the steps below to compare it with the corresponding one in the manifest file, and ensure they match exactly. For example:

### OSX

```
shasum --check borderwallets.txt

borderwallets.html: OK
```

### Linux

```
sha256sum --check borderwallets.txt

borderwallets.html: OK
```

### Windows

```
CertUtil -hashfile borderwallets.html SHA256 | findstr /v "hash"
```

Compare result of this command to the appropriate value in borderwallets.txt to ensure they are the same.

## Conclusion

With all these steps complete you can be certain of the integrity of your download and can proceed to move the file called "borderwallets.html" to your **offline, air-gapped machine**.
