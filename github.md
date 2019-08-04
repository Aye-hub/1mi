![show](https://image.lvzhenye.club/article/image/cid52-doc.jpg)

* [:books:官方文档](https://docsify.js.org/ "官方文档")
* [:octocat:github](https://github.com/Aye-hub/1mi "github")
* [:tv:在线演示](https://www.airbus.club)

## git安装

### 下载git
```bash
sudo yum install git
```

> 如果使用Ubuntu系统，运行`sudo apt-get install git`

### 配置git
```bash
git config --global user.name "Your Name" 
git config --global user.email "email@example.com"
```

### 查看git配置是否生效
```bash
git config --list
```

### 配置远程仓库
```bash
ssh-keygen -t rsa -C "your_email@youremail.com"
```

> 一路回车即可，在`root`目录下`.ssh`文件夹内会生成`id_rsa`、`id_rsa.pub`

## 在GitHub中配置SSH keys，并创建仓库

### 配置SSH keys
首先我们进入`GitHub`官网，点击右上角头像，选择`Settings`，然后选择`SSH and GPG keys`，在右边新建一个`SSH keys`。把上一步生成的`id_rsa.pub`填写到`key`下方，`Title`可以随意填写。

### 创建仓库
我们点击头像左边的`+`号，点击`New repository`创建一个新的仓库。

> 输入仓库名，其他保持默认即可。

#### 初始化仓库
在本地新建一个文件夹`mydoc`
```bash
mkdir mydoc
```
初始化git
```bash
git init
```
初始化完成，我们来测试一下。
```bash
vim readme.txt
```

> 在`readme.txt`里写一句话，然后输入`:wq`退出。

```bash
git add .
git commit -m "新建readme.txt"
git push origin master
```

> 然后刷新刚才创建的仓库，发现已经成功提交了。

## 安装npm

### 下载npm
```bash
wget https://nodejs.org/dist/v10.15.3/node-v10.15.3-linux-x64.tar.xz
```
### 解压
```bash
xz -d node-v10.15.3-linux-x64.tar.xz
tar -xvf node-v10.15.3-linux-x64.tar
```
### 把解压的文档移动到别的目录
```bash
mv node-v10.15.3-linux-x64 /usr/local/lib 
mv /usr/local/lib/node-v10.15.3-linux-x64/ /usr/local/lib/nodejs
```
### 添加环境变量
```bash
export PATH=/usr/local/lib/nodejs/bin:$PATH
```
### 创建链接
```bash
ln -s /usr/local/lib/nodejs/bin/node /usr/bin/node 
ln -s /usr/local/lib/nodejs/bin/npm /usr/bin/npm 
ln -s /usr/local/lib/nodejs/bin/npx /usr/bin/npx
```

> 可以使用`node -v`、`npm version`来查看版本信息。

## 使用docsify

### 安装
```bash
npm i docsify-cli -g
```
### 初始化
进入`mydoc`文件夹
```bash
docsify init ./docs
```

### 本地预览网站
```bash
docsify serve docs
```

> 通过`docsify serve`能运行一个本地服务器，方便预览。默认访问路径：[http://localhost:3000](http://localhost:3000/)
> 如果大家使用云服务器，那么默认访问路径为：[http://<你的服务器ip>:3000/](http://<你的服务器ip>:3000/)
> 记得要放行3000端口。

[scode type="yellow"]如果下载缓慢的话，可以安装国内镜像来提升速度[/scode]
### 国内npm镜像
```bash
npm config set registry https://registry.npm.taobao.org
```

## GitHub Pages

#### 点开仓库，选择` Settings`，往下拉找到`GitHub Pages`，按下图所示选择。

![page](https://image.lvzhenye.club/article/image/cid52-1.png)

> 此时，点击上方分配的免费域名就看到页面了。

## 配置自定义域名
在`Custom domain`选项中，填写自己的二级域名地址，点击`save`。使用自定义域名前，需要在域名商进行`CNAME`解析。记录值填写 `yourname.github.io`，其中`yourname`替换为你的`github`用户名。然后返回`github`官网等待域名证书，证书下发成功后，勾选`GitHub Pages`下的`Enforce HTTPS`按钮，刷新页面就可以了。