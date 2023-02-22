# SED

By default `sed` prints to the STDOUT and does not change the file, to change inline add the `-i` option. Don't forget to add a backup.

## Replace word in text

```sh
sed 's/\bOLD_WORD\b/NEW_WORD/g' file
```

The `\b` is used to establish the boundary and not replace the pattern `OLD_WORD` in the middle of anothe word

## Delete lines that have pattern

```sh
sed '/WORD/d' file
```

### Links
https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux