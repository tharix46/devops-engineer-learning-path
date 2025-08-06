# 👤 Users and Groups in Linux

**Users** and **groups** help manage access to files and resources securely. Every user has an entry in the `/etc/passwd` file, and every group is defined in `/etc/group`.

## 🙍‍♂️ Users

A user is an **individual account** that can log in to the system. Each user has a unique User ID (UID) and can own files and processes.

### Create a user

```bash
sudo useradd -m -s /bin/bash alice
```

- `-m`: create a home directory.
- `-s`: specify the default shell.

### Set a password for the user

```bash
sudo passwd alice
```

### Delete a user

```bash
# delete a user (keep home directory)
sudo userdel alice

# delete a user and remove home directory
sudo userdel -r alice
```

## 🧑‍🤝‍🧑 Groups

A group is a **collection of users.** You can create a group to manage permissions collectively.

### Create a group

```bash
sudo groupadd developers
```

### Delete a group

```bash
sudo groupdel developers
```

### Add a user to a group:

```bash
sudo usermod -aG developers alice
```

### Remove a user from a group

```bash
sudo gpasswd -d alice developers
```

## 🔍 View user and group information

### View user and group IDs:

```bash
id alice
```

### View groups a user belongs to:

```bash
groups alice
```

### /etc/passwd file

Stores basic user info. Each line has 7 fields:

```bash
cat /etc/passwd
```

```plaintext
username:password:UID:GID:GECOS:home_directory:shell
alice:x:1001:1001:alice:/home/alice:/bin/bash
```

### /etc/group file

Stores group information. Each line has 4 fields:

```bash
cat /etc/group
```

```plaintext
groupname:password:GID:user_list
developers:x:1002:alice,bob
```
