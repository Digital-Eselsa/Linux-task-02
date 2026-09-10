# Command Reference

This file organizes the commands required or directly implied by the supplied lab.

> Run commands in your Kali Linux terminal. Replace placeholders only where necessary. Do not treat this file as evidence that the commands were actually executed.

## Step 1 — Create and Switch to `student01`

```bash
sudo adduser student01
sudo usermod -aG sudo student01
su - student01
whoami
```

The lab requires creating `student01`, setting a password, adding the user to `sudo` if required, switching to the user, and confirming with `whoami`.

## Step 2 — Directory and File Management

```bash
mkdir project
cd project
mkdir docs scripts bin
cd docs
echo "This is the initial report by student01." > report.txt
ls -la
echo "Top Secret." > .secret.txt
```

## Step 3 — Edit and Move Files

Open the report:

```bash
nano report.txt
```

Add:

```text
Appended line using nano.
```

Then:

```bash
cp report.txt ../scripts/
mv .secret.txt ../bin/classified.txt
```

Create the required script:

```bash
cd ../scripts
nano install.sh
```

Script content:

```bash
#!/bin/bash
echo "Installing project dependencies..."
```

## Step 4 — Permissions with `chmod`

Make `install.sh` executable by all users:

```bash
chmod a+x install.sh
```

Remove read permission for others from `classified.txt`:

```bash
chmod o-r ../bin/classified.txt
```

Create the admin notes file and allow only the owner to read/write:

```bash
cd ../docs
touch admin_notes.txt
chmod 600 admin_notes.txt
```

## Step 5 — Cleanup and Backup

Delete `admin_notes.txt`:

```bash
rm admin_notes.txt
```

Create the backup directory:

```bash
cd ..
mkdir backup
cp -r docs/* backup/
cp -r scripts/* backup/
```

If hidden files are present and need to be included, use an appropriate method that also handles dotfiles; the original lab specifically says to copy the entire content of `docs` and `scripts` into `backup`.

## Final Checks

Return to the home directory:

```bash
cd ~
```

Install `tree` only if it is not already installed:

```bash
sudo apt install tree
```

Display the project tree:

```bash
tree project
```

Confirm files and permissions:

```bash
ls -la project/docs
ls -la project/scripts
ls -la project/bin
ls -la project/backup
```

## Bonus — Command History

```bash
history
history > commands_used.txt
```

The lab specifies saving the history output to `commands_used.txt` in the user's home directory.
