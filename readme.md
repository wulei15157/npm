﻿1.需求由来
由于node安装插件是从国外服务器下载，受网络影响大，速度慢且可能出现异常。所以如果npm的服务器在中国就好了，所以我们乐于分享的淘宝团队（阿里巴巴旗下业务阿里云）干了这事。来自官网：“这是一个完整 npmjs.org 镜像，你可以用此代替官方版本(只读)，同步频率目前为 10分钟 一次以保证尽量与官方服务同步。

也就是说我们可以使用阿里布置在国内的服务器来进行node安装。

2.使用方法
1.使用阿里定制的 cnpm 命令行工具代替默认的 npm，输入下面代码进行安装：

$ npm install -g cnpm --registry=https://registry.npm.taobao.org
2.检测cnpm版本，如果安装成功可以看到cnpm的基本信息。

cnpm -v
3.以后安装插件只需要使用cnpm intall即可

假如我已经习惯了npm install的安装方式，我不想去下载阿里的cnpm命令工具将命令变成cnpm怎么办？很容易我们想到，我直接将node的仓库地址改成淘宝镜像的仓库地址不就好了吗？

3.单次使用
npm install --registry=https://registry.npm.taobao.org
4.永久使用
设置成全局的下载镜像站点，这样每次install的时候就不用加--registry，默认会从淘宝镜像下载，设置方法如下：

1.打开.npmrc文件（nodejs\node_modules\npm\npmrc，没有的话可以使用git命令行建一个( touch .npmrc)，用cmd命令建会报错）
2.增加 registry =https://registry.npm.taobao.org  即可。
也可以按如下方式直接在命令行设置

npm config set registry https://registry.npm.taobao.org
检测是否成功

// 配置后可通过下面方式来验证是否成功
npm config get registry
// 或
npm info express
这样，我们可以使用淘宝镜像还不用更换成cnpm,是不是很爽！虽然实际都是使用的是淘宝镜像。
最后附上淘宝镜像官网地址：http://npm.taobao.org/

注：如果想还原npm仓库地址，只需再把地址配置成npm镜像就可以了

   npm config set registry https://registry.npmjs.org/
