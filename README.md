# My-linux-server-setting

**install zsh, oh-my-zsh**

for Ubuntu
```bash
apt update && apt install zsh curl
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**zsh setting**
```bash
cat << EOF >> .zshrc
# Custom Shell Setting
set -o vi
force_color_prompt=yes
EOF
```

use powerlevel10k theme (https://github.com/romkatv/powerlevel10k)
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
ln -s ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k/powerlevel10k.zsh-theme ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k.zsh-theme
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="powerlevel10k"/g' ~/.zshrc >
```

