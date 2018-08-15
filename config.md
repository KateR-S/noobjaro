# set up new

## update packages
`sudo pacman -Sy`

## install pacaur
`sudo pacman -S pacaur`

## get at this doc in github

install chrome

`pacaur -S google-chrome`

log in to google

log in to github to grab this info for copy and paste !

## lastpass

### install lastpass cli
`sudo pacman -S lastpass-cli`

### login to lastpass
`export LPASS_HOME=~/.lpass && export LPASS_AGENT_TIMEOUT=0 && lpass login kate.hv.fulcher@gmail.com`

# copy from old

## ssh keys to lastpass
read -sp "ssh passphrase?" passphrase && printf "Passphrase: ${passhprase}\nPrivate Key: $(cat ~/.ssh/id_rsa)\nPublic Key: $(cat ~/.ssh/id_rsa.pub)" | lpass add my_ssh_keys --note-type=ssh-key --non-interactive
