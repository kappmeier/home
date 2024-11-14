# Home

My home directory for Ubuntu machines.

## Add to a computer

```
alias home="git --work-tree=$HOME --git-dir=$HOME/.home.git"
home init
home remote add origin git@github.com:kappmeier/home.git
home fetch --all
home reset --hard origin/main
```


## Initialization

On a new machine, a new SSH key must be created (or the existing Key retrieved
elsewhere.

```
ssh-keygen -t ed25519 -C "jp.kappmeier@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

