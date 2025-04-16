# 🧰 StillNotRaided Setup Guide

## 1. Clone This Template

Click “Use this template” on GitHub, or:

```bash
git clone https://github.com/YOUR_USERNAME/stillnotraided.git
cd stillnotraided
```

## 2. Set Up Secrets

Go to **Settings > Secrets and variables > Actions**, and add the following secrets:

- `GPG_PRIVATE_KEY` – your ASCII-armored private GPG key
- `GPG_PASSPHRASE` – the passphrase for that key
- `GPG_KEY_ID` – your full GPG key ID (optional but recommended)

## 3. Configure GitHub Pages

1. Go to **Settings > Pages**
2. Set source to the `gh-pages` branch and root folder (`/`)
3. Save

## 4. Trigger Your First Update

1. Go to the **Actions** tab
2. Run the **Manual Canary Update with Timestamp** workflow
3. Your signed canary will be published to GitHub Pages

✅ Done! You’re StillNotRaided — for now.
