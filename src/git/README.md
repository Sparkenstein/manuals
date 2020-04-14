# Git

## Signing your commits:

- First generate the gpg key

```bash
gpg --full-generate-key
```

And answer the questions. Make sure email is same as github account

- Then we need to get Key ID:

```bash
gpg --list-secret-keys --keyid-format LONG
```

or if you are running `gpg2`

```bash
gpg2 --list-keys --keyid-format LONG
```

Copy the key id. it should be in the format `encryption/keyid/` example: `rsa4096/E43E1234E6ABCDEC 2019-04-14 [SC]`

Then exort the key with

```bash
gpg --armor --export E43E6031E6CFF4EC
```

it should print your public key. copy everything from `-----BEGIN PGP PUBLIC KEY BLOCK-----` till end `-----END PGP PUBLIC KEY BLOCK-----` 
and paste it in your github settings.


- Now we need to tell git to use these keys. Simply copy the previous Key ID and paste in the following command

```bash
git config --global user.signingkey E43E1234E6ABCDEC
```

Also make sure the git user has the same email with

```bash
git config --global user.email
```
