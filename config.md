# set up new

## set fonts
stuff always seems to be tiny in manjaro install so set fonts


## update packages
`sudo pacman -Sy`

## install pacaur
`sudo pacman -S pacaur`

## get at this doc in github

install chrome

`pacaur -S google-chrome`

log in to google

log in to github to grab this info for copy and paste !

## connect to the githubs

### install lastpass cli

`sudo pacman -S lastpass-cli`

### login to lastpass

`export LPASS_HOME=~/.lpass && export LPASS_AGENT_TIMEOUT=0 && lpass login kate.hv.fulcher@gmail.com`

### export keys and set them up

```
lpass show my_ssh_keys --field="Public Key" | install -D /dev/stdin ~/.ssh/id_rsa.pub && lpass show my_ssh_keys --field="Private Key" | install -D /dev/stdin ~/.ssh/id_rsa
chmod 400 ~/.ssh/id_rsa
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```
test them

`ssh -T git@github.com`

### clone this
`git clone git@github.com:KateR-S/utils`

## install gpg keys

```
lpass show my_gpg_key --field="Private Key" | gpg --import
```
## Install packages

### Leiningen

Download script from https://leiningen.org/ to `/bin/lein.sh`

```
sudo chmod a+x /bin/lein.sh
/bin/lein.sh
```

# copy from old

## ssh keys to lastpass
`read -sp "ssh passphrase?" passphrase && printf "Passphrase: ${passhprase}\nPrivate Key: $(cat ~/.ssh/id_rsa)\nPublic Key: $(cat ~/.ssh/id_rsa.pub)" | lpass add my_ssh_keys --note-type=ssh-key --non-interactive`

## gpg keys to lastpass

List keys. Grab Id
`gpg --list-keys`

With ID from above...

`printf "Private Key: $(gpg --export-secret-keys -a $ID) | lpass add my_gpg_key --note-type=ssh-key --non-interactive`
