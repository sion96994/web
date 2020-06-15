# Node环境搭建

## 搭建内容
  [node安装](https://nodejs.org/zh-cn/)

  前端工程依赖node环境,依赖管理需要node集成的```npm```包管理工具;

  [nvm安装](https://github.com/nvm-sh/nvm/blob/master/README.md)

  在多项目开发中,每个项目依赖的Node环境不一样,使用nvm管理node版本切换;

  [nrm安装](https://www.npmjs.com/package/nrm)

  npm仓库地址在国外,获取依赖时下载速度较慢.使用```nrm```管理仓库地址切换;

  [yarn安装](https://yarn.bootcss.com/)

  比npm更快,更高效的包管理工具.

---

## nvm安装

使用nvm来管理node的情况下,不需要单独下载Node.我们通过nvm来下载node.

<p style="color:red">千万不要使用brew安装nvm</p>

Install 
```
第一步

  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
  或者
  wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash

第二步

  vi ~./zshrc  #配置nvm环境变量
  export NVM_DIR="${XDG_CONFIG_HOME/:-$HOME/.}nvm"
  [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```
Use
```
  nvm install stable         #安装最新稳定版本的node
  node -v                    #安装后查看node版本

  其他nvm常用命令
  nvm install version        #安装版本号为 `version` 的node版本
  nvm ls                     #查看已下载的node版本,和正在使用的node版本
  nvm alias default version  #设置默认的node版本为 `version`
  nvm use version            #切换node版本为 `version`
  nvm --helop                #查看更多nvm的其他命令
```
---
## nrm的安装
Install
```
  npm install -g nrm
```
Use
```
  nrm ls                        #查看可选的源,和当前使用源
  nrm use target                #使用`target`目标源
  nrm add <registryName> <url>  #增加新npm地址仓库地址(在公司私有npm情况时使用)
  nrm del registryName          #删除指定源(在公司私有npm情况时使用)
  nrm test registryName         #测试相应源的时间
```
---
## yarn的安装
Install
```
  brew install yarn --ignore-dependencies    #使用nvm时,该命令不会再下载node,会使用nvm的node
  which node                                 #查看一下node的真实目录
```
Question
```
  brew doctor                                       #看看是否有依赖错误(历史问题)
  若有`brew install node`提示
  ln -s ~/.nvm/versions/ /usr/local/Cellar/node     #为Node执行软连接
  brew doctor                                       #再次检查依赖错误
```
Use
```
  yarn init                      #初始化项目
  yarn                           #安装项目全部依赖
  yarn remove packageName        #移除包名为`packageName`的依赖 
  yarn add packageName           #下载包名为`packageName`的依赖
  yarn globa add packageName     #全局安装包名为`packageName`的依赖
```
