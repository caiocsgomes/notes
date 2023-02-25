# GPG commands

Import keys

```bash
gpg --import KEY
```

List keys
```bash
gpg --list-keys
gpg --list-secret-keys
```

Refresh keys
```bash
gpg --refresh-keys
```

Encrypt
```bash
gpg --output encrypted_me.asc --encrypt --recipient --armor kodekloud@kodekloud.com encrypt_me.txt
```

Decrypt 
```bash
gpg --output decrypted_me.txt --decrypt --recipient kodekloud@kodekloud.com decrypt_me.asc
```