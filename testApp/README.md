# 快应用功能把玩

## 环境安装

快应用的环境可以说是比较简单的了

首先, 我们需要安装node, 应该研究快应用的都已经安装过了node了

mac用户推荐使用`nvm`对node进行版本管理

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
nvm --version
```

然后运行`nvm`查看下nvm是够安装成功

使用nvm安装node的最大好处是我们随时可以对node进行版本替换, 不论我们之前用的node版本是什么, 都可以通过nvm进行对应的管理

```
nvm install 8.11.3
```

如上, 我们成功安装了node的8.11.3版本

win用户就更简单了, 直接到nodejs官网下载最新版的安装包即可

> 注意: 因为hap-toolkit对node v8.0.x不兼容, 所以不要下载这类的版本, 其他的版本都可以, 比如说我安装的是最新的稳定版本8.11.3, 亲测可行

安装好之后可以查看node及对应的npm版本, 保证安装成功

```
node -v
npm -v
```

## hap-toolkit安装

安装好之后可以使用node来安装快应用的开发工具

```
npm i -g hap-toolkit
```

安装好之后, 就可以在全局使用hap命令了

```
hap -V
```

注意这个v是大写的

同时, 我们需要在android手机上安装好快应用调试器工具, 地址如下

https://www.quickapp.cn/docCenter/post/69

## 创建个项目玩一玩

```
hap init myProject
cd myProject
npm install
```

以上三行命令让我们安装了一个模板, 并安装好了模板的所有依赖

## 运行项目

```
npm run server
```

上面的命令让我们开启了快应用的开发服务, 此时如果没有指定端口, 就是默认的12306端口, 我们可以通过chrome浏览器进行访问

```
localhost:12306
```

此时可以看到二维码的界面, 我们使用安卓手机上安装好的软件扫码, 即可进入之前初始化的模板页面

同时, 我们保持当前的terminal开启, 再开启一个terminal, 运行下面的命令

```
npm run watch
```

这个命令为我们开启了一个实时的热刷新功能, 我们在代码上的更新会被实时编译到手机上

至此, 整个项目初始化并开启服务完成

happy haking!

## 注意点:

我在安装好依赖之后尝试运行项目, 会报错一个依赖没有找到, 后面尝试了社区中的方法, 就恢复了

解决方法是对toolkit进行强制升级

报错时运行如下代码

```
hap update --force
```
