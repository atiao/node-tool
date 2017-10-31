1.项目文件里需要package.json来管理本地安装的npm包。
  npm init
  注意下 index.js 入口，后续在这里面搞事情。

2.#!/usr/bin/env node 算是unix/linux 的写法，意思就是指定node为脚本解释语言.

3.因为我们做的是一个本地全局使用的工具，所以需要在package.json中配置bin字段，他是一个命令名和本地文件名的映射。

4.npm link 安装本地模块，并将本地模块cli化