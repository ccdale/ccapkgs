# ccapkgs

## register pacman repo

```bash
[ccapkgs]
SigLevel = Optional TrustAll
Server = https://raw.github.com/ccdale/$repo/main/any
```

## add/update package

```bash
cd ~/src/ccapkgs/any/

# -R removes old versions
repo-add -R ccapkgs.db *.pkg.tar.zst
git commit -a -m "added/updated package ..."
git push
```
