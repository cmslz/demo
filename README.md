# PHP composer 包 自制打包流程DEMO
## 一、 git 创建仓库
## 二、 git 拉取仓库
## 三、 composer.json 文件编写
```
{
  "name": "cmslz/demo", // 包名称
  "description": "cmslz-demo", // 包描述
  "version": "cmslz-demo", // 包的版本:格式必须是 X.Y.Z，选择性后缀：-dev、-alphaN、-betaN、-RCN。
  "type": "library", // 包类型: library：默认值。它将复制文件到 vendor 目录。project：它表示这是个项目，而不是库。比如像 Symfony 标准版这种应用。metapackage：一个含有依赖的空包，能触发安装，但不包含文件，不会向文件系统写任何东西。composer-install：为其他的定制类型的包提供安装器的包。
  "keywords": ["demo","php","cmslz"], // 一个与包相关的关键词数组。用于包的搜索和过滤
  "homepage": "https://github.com/cmslz/demo", // 项目的网站 URL
  "time":"", // 版本发布时间。必须是 YYYY-MM-DD 或 YYYY-MM-DD HH:MM:SS 格式。
  "license": "MIT", // 包的许可证。可以是字符串或字符串数组
  "authors": [ // 包的作者。是个对象数组 name、email、homepage(作者网站 URL)、role(作者在项目中的角色（如：developer 或 translator）)
    {
      "name": "cmslz",
      "email": "heqiangchun0221@foxmail.com"
    }
  ],
  "require": {
    "php": "^7.4"
  },
  "autoload": {
    "files": [
      "src/helpers.php"
    ],
    "psr-4": {
      "Cmslz\\Demo\\": "src/"
    }
  },
  "autoload-dev": {
    "files": [
      "src/helpers.php"
    ],
    "psr-4": {
      "Cmslz\\Demo\\": "src/"
    }
  },
  "suggest":{
    "cmslz/demo":"请安装这个应用，不然不能使用"
  }
}
```
## 四、 初始化仓库自动加载
```shell
composer dumpautoload -o
```
