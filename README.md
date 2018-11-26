# Git Commit Signing Using GPG

## Setup

For more information, visit [Generating a new GPG key](https://help.github.com/articles/generating-a-new-gpg-key).

> Your GPG key must use RSA with a key size of 4096 bits.

```
gpg2 --full-gen-key
```

## Configure

From your Git repository, execute the following set of commands.

### Signing Parameters

```
git config --local commit.gpgsign 'true'
git config --local gpg.program 'gpg2'
```

### Identity Parameters

```
git config --local user.name 'John Doe'
git config --local user.email 'john@doe.com'
git config --local user.signingkey 'Thumbprint'
```

## Usage

```
git commit -S -m 'Your Commit Message'
```

## Verify

```
git cat-file commit HEAD

tree 5ef701a43a7ad615c5442517fc1d9fcdf140ca28
author Darin Egan <5701436+darinegan@users.noreply.github.com> 1542804946 +0000
committer Darin Egan <5701436+darinegan@users.noreply.github.com> 1542967470 +0000
gpgsig -----BEGIN PGP SIGNATURE-----
 Version: GnuPG v2

 iQIcBAABCAAGBQJb99CuAAoJED6ugZJ/eyqwpTcP/jEozFRON8+G4D8l5Gv8hK0T
 ...
 1QIlgFkE2U+00m3+eKHJ
 =wz7/
 -----END PGP SIGNATURE-----

Genesis
```

## References

- [Telling Git about your signing key](https://help.github.com/articles/telling-git-about-your-signing-key)
- [Signing commits](https://help.github.com/articles/signing-commits)
- [Signing tags](https://help.github.com/articles/signing-tags)

Fin.
