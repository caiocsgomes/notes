# delete files in a folder not owned by specific user

```bash
find FOLDER ! -user USER -type f -delete
```