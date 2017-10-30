# static-resource
静态资源管理

## 第一步：安装工具

这个命令行小工具依赖 [nodejs](http://nodejs.org/) 环境，因此，请先确保本地安装了它。

使用 [nodejs](http://nodejs.org/) 随带的 [npm](https://www.npmjs.org/) 包管理工具进行安装：

```bash
npm install -g lg-static-resource
```

## 第二步：创建项目

```bash
mkdir rsd-project
cd rsd-project
```

在项目根目录下创建一个空的 ``fis-conf.js`` 文件，空着就行。

然后开始在项目目录下，建自己的文件目录！

## 第三步：发布代码

在项目根目录下执行：

```bash
lgrsd release --md5 --dest ../output
```

然后去到 ``../output`` 目录下去查看一下产出结果吧，所有静态资源都以md5摘要形式发布了出来，所有资源链接，我说 **所有链接**，包括html中的图片、样式、脚本以及js中的资源地址、css中的资源地址全部都加上了md5戳。

上述命令中，``--md5`` 就是表示要给所有资源定位标记加上摘要信息的意思，不加这个参数就没有摘要信息处理。``--dest ../output`` 表示把代码发布到当前目录上一级的output目录中。整个这条命令还可以简写成：

```bash
lgrsd release -md ../output
```

## 把代码发布指定位置：

```bash
lgrsd release -md d:\wwwroot
```

如果你本地没有安装任何服务器，你可以使用lg-static-resource内置的调试服务器，执行命令：

```bash
lgrsd server start
```

接下来我们同样要把代码发布到这个内置服务器中，release命令如果省略 ``--dest <path>``参数，就表示把代码发布到内置服务器的根目录下：

```bash
lgrsd release -m
```

在浏览器中访问： http://localhost:8080 即可