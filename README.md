# Readme

## Setup

For more information, visit [Generating a new GPG key](https://help.github.com/articles/generating-a-new-gpg-key).

> Your GPG key must use RSA with a key size of 4096 bits.

```
gpg2 --full-gen-key
```

## Configure

From your Git repository, execute the following set of commands.

```
git config --local commit.gpgsign 'true'
git config --local gpg.program 'gpg2'
```

```
git config --local user.name 'John Doe'
git config --local user.email 'john@doe.com'
git config --local user.signingkey 'Thumbprint'
```

### Verify

```
git config --list --local
```

## Usage

```
git commit -S -m 'Your Commit Message'
```

### Verify

```
git cat-file commit HEAD
```

## References

- [Telling Git about your signing key](https://help.github.com/articles/telling-git-about-your-signing-key)
- [Signing commits](https://help.github.com/articles/signing-commits)
- [Signing tags](https://help.github.com/articles/signing-tags)

Fin.
