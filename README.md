# 🐤 StillNotRaided

*A self-hosted cryptographic warrant canary.*  
Because you haven’t been raided. Yet.

---

## 📜 What It Is

StillNotRaided is a minimalist warrant canary kit you can host yourself using GitHub Pages. It provides a timestamped, GPG-signed document affirming that you have not received secret subpoenas, gag orders, or other sealed legal processes.

---

## 🛠️ How It Works

- Canary files (`canary.txt` and `canary.txt.sig`) are stored in the `pages/` folder.
- A GitHub Actions workflow updates the timestamp, signs it with GPG, and pushes the result to the `gh-pages` branch.
- GitHub Pages publishes the canary at:

```
https://<your-username>.github.io/stillnotraided/
```

---

## ✅ Manual Update Process

1. Set up your secrets in GitHub (see `setup.md`)
2. Trigger the **Manual Canary Update with Timestamp** workflow from the Actions tab
3. The updated canary will be timestamped, signed, and published

---

## 🔐 GPG Signature Verification

Use your GPG public key to verify:

```bash
gpg --verify canary.txt.sig canary.txt
```

---

## ⚠️ Expiration Policy

If the canary isn’t updated within 14 days, assume something’s wrong. This could mean the maintainer is under legal obligation not to update it.

---

## 📦 Version

`v1.0.0`
