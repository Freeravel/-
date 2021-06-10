#deepin下zsh的安装与使用


1.安装zsh
sudo apt install zsh
chsh -s /bin/zsh

2.安装oh-my-zsh
基于zsh命令行，是对zsh的包装，提供了主题配置，插件机制.
curl
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
wget
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

3.安装Powerlevel9k / Powerlevel10k主题
zsh使用最多的主题
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
编辑 ~/.zshrc 设置 ZSH_THEME="powerlevel10k/powerlevel10k"
再增加一行配置:POWERLEVEL9K_MODE="awesome-patched"

4.安装字体
apt-get install fonts-powerline

5.zsh配置主题
source ~/.zshrc
或者执行下面的命令,重新配
p10k configure
开始配置Powerlevel10k,根据提示(喜好)选择1234或yes、no

6.一些常用的插件
zsh-autosuggestions
下载插件
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
编辑 ~/.zshrc ,设置plugins
plugins=(zsh-autosuggestions git)
使插件生效
source ~/.zshrc
上次敲过的命令 ,会自动提示,按右方向键➡️确认填充上次的命令
zsh-syntax-highlighting
下载插件
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
写入到配置
echo "source $ZSH_CUSTOM/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc

使插件生效
source ~/.zshrc
命令会自动高亮显示
