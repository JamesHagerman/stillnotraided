# 🧰 StillNotRaided Setup Guide

## 1. Clone This Template

Click “Use this template” on GitHub, or:

```bash
git clone https://github.com/YOUR_USERNAME/stillnotraided.git
cd stillnotraided
```

## 2. Generate a GPG Key (if you don't already have one)

You need `gpg` installed to generate and manage your cryptographic keys. See below for install directions.

Run the following in your terminal:

```bash
gpg --full-generate-key
```

Choose:
- Key type: **RSA and RSA**
- Key size: **4096 bits**
- Expiration: your choice (e.g. 1 year)
- Name/email: your identity (used for signatures)
- Passphrase: secure but memorable

List your keys:

```bash
gpg --list-secret-keys --keyid-format LONG
```

Look for your key ID in the output, e.g.:

```
/Users/you/.gnupg/secring.gpg
------------------------------------
sec   rsa4096/ABC1234DEF5678 2025-01-01 [SC]
```

## 3. Export Your GPG Private Key (for GitHub Actions)

Export the private key and copy the output:

```bash
gpg --export-secret-keys --armor ABC1234DEF5678
```

Also export your public key if you want to publish it:

```bash
gpg --export --armor ABC1234DEF5678 > public-key.asc
```

## 4. Add Secrets to GitHub

Go to **Settings > Secrets and variables > Actions**, and add:

| Secret Name       | Value                                    |
|-------------------|------------------------------------------|
| `GPG_PRIVATE_KEY` | Output of `--export-secret-keys --armor` |
| `GPG_PASSPHRASE`  | Your passphrase from key creation        |
| `GPG_KEY_ID`      | Your long key ID (e.g. ABC1234DEF5678)   |

## 5. Configure GitHub Pages

1. Go to **Settings > Pages**
2. Set source to the `gh-pages` branch and root folder (`/`)
3. Save

## 6. Trigger Your First Update

1. Go to the **Actions** tab
2. Run the **Manual Canary Update with Timestamp** workflow
3. Your signed canary will be published to GitHub Pages

✅ Done! You’re StillNotRaided — for now.


---

## 💾 Installing GPG (GnuPG)

You need `gpg` installed to generate and manage your cryptographic keys. Here’s how to install it on major platforms:

### 🐧 Linux (Debian/Ubuntu)
```bash
sudo apt update
sudo apt install gnupg
```

### 🐧 Linux (Arch-based)
```bash
sudo pacman -S gnupg
```

### 🍏 macOS (via Homebrew)
```bash
brew install gnupg
```

> 💡 Homebrew: https://brew.sh

### 🪟 Windows

1. Download Gpg4win (includes GnuPG + Kleopatra GUI):  
   👉 https://gpg4win.org

2. During installation, ensure **GnuPG** and **Kleopatra** are checked

3. After install, restart your terminal or use Kleopatra to generate keys with a GUI
