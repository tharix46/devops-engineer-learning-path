# 📁 File Permissions in Linux

File permissions help control **who** can read, write, or execute a file or directory.

## 🔐 Symbolic Permissions

User types:

- `u` → **user** (owner)
- `g` → **group**
- `o` → **others**

Permissions:

- `r` → **read**
- `w` → **write**
- `x` → **execute**

Operators:

- `+` → **add** permission
- `-` → **remove** permission
- `=` → **set exactly** (override)

### 🧪 Examples

```bash
# Add execute permission for user
chmod u+x script.sh

# Remove write permission from group
chmod g-w file.txt

# Set read-only for everyone. `a` means all (user, group, others)
chmod a=r file.txt

# Custom permission set for user, group, others
chmod u=rw,g=r,o= file.txt
```

## 🗂️ Numeric Permissions

Each permission has a number:

- `r` = **4**
- `w` = **2**
- `x` = **1**

To calculate total:

- `7` = 4 + 2 + 1 → **read + write + execute**
- `6` = 4 + 2 → **read + write**
- `5` = 4 + 1 → **read + execute**
- `0` = **no permissions**

**Permissions** are defined in **three digits: user-group-others** (755, 644, etc.).

### 🧪 Examples

```bash
# rwx for user, rx for group and others
chmod 755 script.sh

# rw for user, r for group and others
chmod 644 notes.txt

# full access for user only
chmod 700 secret.sh
```

## Ownership

Every file or directory has an owner and a group. To view ownership `ls -l` command is used.

To change owner:

```bash
sudo chown username file.txt
```

To change group:

```bash
sudo chgrp groupname file.txt
```

To change both owner and group:

```bash
sudo chown username:groupname file.txt
```

### 🧪 Examples

```bash
# Change owner to alice
sudo chown alice document.txt

# Change owner to bob and group to developers
sudo chown bob:developers script.sh
```
