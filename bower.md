### Bower是一个客户端技术的软件包管理器，它可用于搜索、安装和卸载如JavaScript、HTML、CSS之类的网络资源。
## 使用准备
- 安装npm
- 安装git
- 使用npm install bower -g
## bower 的基本使用
1. 在项目目录 `touch .bowerrc`
```
{
    "directory": "libs"
}
//定义bower 下载包的存放路径，默认是bower_conponents
```
2. bower init   
根据提示，操作就可创建一个，bower.json文件，这个文件是管理包依赖的；
3. `核心操作`bower install  
安装所需要的包，可以指定参数
--save 将所安装的包写入bower.json文件中的dependencies中;
--save-dev 写入 devDependencies字段中；
4. bower 可以安装指定版本的包，语法 bower install name#版本号
