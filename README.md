# Home

My home directory for Ubuntu machines.

## Add to a computer

```bash
alias home="git --work-tree=$HOME --git-dir=$HOME/.home.git"
home init
home remote add origin git@github.com:kappmeier/home.git
home fetch --all
home reset --hard origin/main
```


## Initialization

On a new machine, new keys must be created (or the existing key retrieved elsewhere). The following
example shows how to set up authentication and signing with SSH keys. Observe, that GPG keys could
be used for signing as well.

### Create new SSH keys

```bash
ssh-keygen -t ed25519 -C "jp.kappmeier@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
ssh-keygen -t ed25519 -C "jp.kappmeier@gmail.com" -f ~/.ssh/id_ed25519_signing
ssh-add "$HOME/.ssh/id_ed25519_signing"
```

# Upload to GitHub

The created keys must be uploaded to GitHub keys. The first as `Authentication Key`, the second as
`Signing Key`.

```bash
cat ~/.ssh/id_ed25519.pub
cat ~/.ssh/id_ed25519_signing.pub
xdg-open "https://github.com/settings/keys"
```
