# linux shell setting
for Ubuntu
**install tmux, zsh, oh-my-zsh**
```bash
apt update && apt install zsh curl tmux
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**tmux setting**
```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
wget https://raw.githubusercontent.com/MinooE/linux-shell-setting/main/tmux.conf -O ~/.tmux.conf
```

**zsh setting**
```bash
cat << EOF >> .zshrc
# Custom Shell Setting
set -o vi
force_color_prompt=yes

# fortune
fortune $HOME/.local/fortune/
EOF
sed -i 's/plugins=(git)/plugins=(\ngit\ntmux\n)/g' ~/.zshrc
```

use powerlevel10k theme (https://github.com/romkatv/powerlevel10k)
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
ln -s ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k/powerlevel10k.zsh-theme ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k.zsh-theme
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="powerlevel10k"/g' ~/.zshrc
```

ssh reconnect
