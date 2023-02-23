# find patterns

- delete all files that do not belong to a user

```bash
find FOLDER ! -user USER -type f -delete
```

- cp all files with given extension from one folder to another
```bash
find . -name '*.php' -exec sudo cp --parents \{\} /ecommerce/ \;
```