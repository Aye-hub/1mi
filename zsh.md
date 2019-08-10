## 安装zsh

### yum安装zsh
```bash
yum -y install zsh
```

### 把shell切换为zsh
```bash
chsh -s /bin/zsh
```

### 重启
```bash
reboot
```

### 查看当前shell
```bash
echo $SHELL
```
> 如果返回`/bin/zsh`则表示成功。

## 安装 oh my zsh

!> 由于oh-my-zsh源码是放在github上，先确保机器已安装git

### 安装
```bash
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```
**成功界面**
```bash
  ____  / /_     ____ ___  __  __   ____  _____/ /_  
 / __ \/ __ \   / __ `__ \/ / / /  /_  / / ___/ __ \ 
/ /_/ / / / /  / / / / / / /_/ /    / /_(__  ) / / / 
\____/_/ /_/  /_/ /_/ /_/\__, /    /___/____/_/ /_/  
                        /____/                       ....is now installed!
Please look over the ~/.zshrc file to select plugins, themes, and options.

p.s. Follow us at https://twitter.com/ohmyzsh.

p.p.s. Get stickers and t-shirts at http://shop.planetargon.com.
```

## 选择主题

### 修改主题
```bash
vim ~/.zshrc
```

**将`ZSH_THEME`改为自己喜欢的主题**

**例如：**
```bash
ZSH_THEME="ys"
```

### 更新配置
```bash
source ~/.zshrc
```