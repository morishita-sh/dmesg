# Install latest neovim

```bash
sudo apt remove neovim
sudo apt install libfuse2
wget https://github.com/neovim/neovim/releases/latest/download/nvim-linux-x86_64.appimage
chmod u+x nvim-linux-x86_64.appimage
./nvim-linux-x86_64.appimage --appimage-extract
sudo mv squashfs-root/usr/bin/nvim /usr/local/bin/nvim
sudo mv squashfs-root/usr/share/nvim /usr/local/share/nvim
rm -rf nvim-linux-x86_64.appimage squashfs-root
```

# Install AstroNvim
```bash
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak
git clone --depth 1 https://github.com/AstroNvim/template ~/.config/nvim
rm -rf ~/.config/nvim/.git
echo "vim.opt.wrap = true" >> ~/.config/nvim/init.lua
nvim
```
