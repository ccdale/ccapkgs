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

# remove old db (not entirely necessary but makes it all easier)
rm ccapkgs.db ccapkgs.files
# -R removes old versions
repo-add -R ccapkgs.db.tar *.pkg.tar.zst
# we now have a couple of symlinks and the .tar files
# we need to remove the symlinks and rename the tar files
# to what the symlink was called
rm ccapkgs.db ccapkgs.files
mv ccapkgs.db.tar ccapkgs.db
mv ccapkgs.files.tar ccapkgs.files
git commit -a -m "added/updated package ..."
git push
```
