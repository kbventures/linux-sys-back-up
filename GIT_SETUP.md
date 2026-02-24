# Git Authentication Setup

## First-time setup (do this once)

```bash
git config --global credential.helper store
git push
```

Enter your credentials when prompted — they'll be saved permanently.

- Username: `kbventures`
- Password: your GitHub Personal Access Token (NOT your GitHub password)

## If it stops working (token expired or revoked)

1. Generate a new token: GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic)
   - Set expiration: **No expiration**
   - Check: **repo**

2. Store it:
```bash
echo "https://kbventures:YOUR_NEW_TOKEN@github.com" > ~/.git-credentials
```

3. Verify:
```bash
cat ~/.git-credentials
```

Should output: `https://kbventures:YOUR_NEW_TOKEN@github.com`

## If it keeps asking for credentials on every push

The credential helper is probably not set. Fix it:

```bash
git config --global credential.helper store
git push
```

Enter credentials once — done.
