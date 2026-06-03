## Verify GPG On System
```bash
gpg --version
```

## Generate GPG Key
```bash
gpg --full-generate-key
    Please select what kind of key you want:
        (1) RSA and RSA

    RSA keys may be between 1024 and 4096 bits long.
    What keysize do you want?
        4096

    Please specify how long the key should be valid.
        0 = key does not expire

    Real name:
        Your_Name

    Email address:
        your_email@domain.tld
```

## Find Your GPG Key ID
```bash
gpg --list-secret-keys --keyid-format LONG
```

Output is sometjing like below:
```bash
sec   rsa4096/ABCDEFGHI123456789LMNOP 2026-07-03 [SC]
      ABCDEFGHI123456789LMNOPABCDEFGHI123456789LMNOP
uid                 [ultimate] Your_Name <your_email@domain.tld>
```

Copy vaalue after `rsa4096`. Here is `ABCDEFGHI123456789LMNOP`.

## Export Your Public GPG Key
```bash
gpg --armor --export <KEY_ID>
```

`<KEY_ID>` is value you copied in last step `(ABCDEFGHI123456789LMNOP)`.
Output is somehing like below:
```bash
-----BEGIN PGP PUBLIC KEY BLOCK-----
...
-----END PGP PUBLIC KEY BLOCK-----
```

## Add Your GPG Key to GitHub
```bash
Profile Picture 
Settings
SSH and GPG Keys
New GPG Key
Title = WhateeverYouWant
Value =
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    ...
    -----END PGP PUBLIC KEY BLOCK-----
Add GPG Key
```

## Configure Git to Sign Commits
```bash
git config --global user.signingkey <KEY_ID>
git config --global commit.gpgsign true
git config --global gpg.program gpg\
```

`<KEY_ID>` is value you copied in last step `(ABCDEFGHI123456789LMNOP)`.

## Configure GPG Terminal Support
```bash
echo 'export GPG_TTY=$(tty)' >> ~/.zshrc
source ~/.zshrc
```
