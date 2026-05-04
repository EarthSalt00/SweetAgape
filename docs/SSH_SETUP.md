# SSH key authentication for Sweet Agape

> **No private keys are committed to this repo.** Generate yours locally and add the **public** key to GitHub. That is the only safe pattern.

## 1. Generate a keypair (Ed25519 recommended)

```bash
ssh-keygen -t ed25519 -C "sweetagape-deploy" -f ~/.ssh/sweetagape_ed25519
```

Press Enter twice to skip the passphrase, or set one for extra protection.

## 2. Add the public key to GitHub

```bash
cat ~/.ssh/sweetagape_ed25519.pub
```

Copy the output, then go to **GitHub → Settings → SSH and GPG keys → New SSH key** and paste it.
For deploy-only access, use **Repo → Settings → Deploy keys** instead.

## 3. Tell SSH which key to use for github.com

Append to `~/.ssh/config`:

```sshconfig
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/sweetagape_ed25519
  IdentitiesOnly yes
```

## 4. Switch this clone to SSH (no password / PAT needed)

```bash
git remote set-url origin git@github.com:EarthSalt00/SweetAgape.git
ssh -T git@github.com   # should greet you by username
git push
```

## 5. Rotate the GitHub PAT you shared in chat

Anything pasted into a chat transcript should be considered leaked. Revoke it now:
**GitHub → Settings → Developer settings → Personal access tokens → Revoke.**
