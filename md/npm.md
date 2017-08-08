## npm 的安装：
- npm是随nodejs 安装时，同步安装的
## npm 的常用命令
- npm install npm -g   
更新到最新版本
- npm help  
查看npm   的常用的指令
- npm -l  
查看各个命令的简单用法
- npm -v    
查看npm 的版本
- npm config list -l  
查看npm 的配置
- npm init  
用来初始化生成一个新的package.json文件，他会向用户提问一系列问题，如果你觉得不需要修改默认的配置,一路回车就可以了。如果使用了-f 就会跳过提问阶段，直接生成一个新的package.json文件，-y 是yes;
- npm set  
用来全局的配置npm的信息，配置存放的地址是用户主目录`~/.npmrc`文件
```
$ npm set init-author-name 'Your name'
$ npm set init-author-email 'Your email'
$ npm set init-author-url 'http://yourdomain.com'
$ npm set init-license 'MIT'
```
- npm info  
查看每个模块的具体信息；
- npm search  
搜索npm 仓库,他后面可以跟字符串或者regExp;
- npm list  
 以树状结构列出当前项目安装的所有模块,以及他们的依赖模块。-g 会列出全局安装的模块,也可以在后面跟一个模块的名字，列出单一模块的依赖；
 - npm install  
 本地模式、全局模式  
 npm在默认情况下会从npm搜索下载包，将包安装到当前目录的node_modules子目录下。全局模式，是安装到npm的根目录下，并且提供注册的`PATH`,可以全局调用，一般只有工具模块才会使用全局安装，如 bower，gulp等；
 ## install
 - install可以指定参数，install默认安装模块的最新版本.
 ```
$ npm install sax@latest
$ npm install sax@0.1.1
$ npm install sax@">=0.1.0 <0.2.0"
```
 ## dependencies
 - npm 的核心内容，依赖管理，这个对象的内容就是我们这个项目所依赖的模块包，放在这给对象下的依赖,在执行npm install时，npm会帮我们下载最新的包，当别人引用我们的包时，包内的依赖会被下载下来.
 ## devDependencies 开发依赖
 - 在我们开发时会用到的一些包，只是在开发环境需要用到，但是别人在用我们的包时，不会用到这些内容,我们放到decDependencies,里面在别人引用时，不会被npm所下载；
```

"devDependencies": {
 "autoprefixer": "^6.4.0",
 "babel-preset-es2015": "^6.0.0",
 "babel-preset-stage-2": "^6.0.0",
 "babel-register": "^6.0.0",
 "webpack": "^1.13.2",
 "webpack-dev-middleware": "^1.8.3",
 "webpack-hot-middleware": "^2.12.2",
 "webpack-merge": "^0.14.1",
 "highlightjs": "^9.8.0"
}
```
- 当你有一个完整的package.json文件时，就可以一眼看出这个模块的基本信息，和这个模块所依赖的包.我们可以通过npm install 加载所需要的包.  
install会默认安装dependencise和devDependencies字段中的所有模块，使用--production 可以只安装dependencies字段中的模块，
```
$ npm install --production
# 或者
$ NODE_ENV=production npm install
```
一旦安装了某个模块，就可以使用require加载这个模块；
```
–save：模块名将被添加到 dependencies，可以简化为参数-S。
–save-dev：模块名将被添加到 devDependencies，可以简化为参数-D。
```
- npm bin  
显示当前目录,node模块所执行脚本的所在目录； 

  




