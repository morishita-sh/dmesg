# bash

## ble.sh
- https://github.com/akinomyoga/ble.sh

### Install
```bash
git clone --recursive --depth 1 --shallow-submodules https://github.com/akinomyoga/ble.sh.git
make -C ble.sh install PREFIX=~/.local
echo 'source -- ~/.local/share/blesh/ble.sh' >> ~/.bashrc
```

if needed
```bash
sudo mkdir -p /run/user/1000
sudo chown -R 1000:1000 /run/user/1000
sudo chmod 700 /run/user/1000
```

### Tips
- press `Ctrl-j` for multi line commands


## bash-it
- https://github.com/bash-it/bash-it

### Install
```bash
git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it
~/.bash_it/install.sh
```
