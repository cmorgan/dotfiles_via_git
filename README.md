
https://news.ycombinator.com/item?id=11070797

```
git init --bare $HOME/.myconf
alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
config config status.showUntrackedFiles no
```
then
```
config status
config add .vimrc
config commit -m "Add vimrc"
config add .config/redshift.conf
config commit -m "Add redshift config"
config push
```

when installing:
```
git clone --separate-git-dir=$HOME/.myconf /path/to/repo $HOME/myconf-tmp
cp ~/myconf-tmp/.gitmodules ~  # If you use Git submodules
rm -r ~/myconf-tmp/
alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
```
