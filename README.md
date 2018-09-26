# study
学习记录


- [android应用发布](https://github.com/xkdaq/wxdemo/blob/master/article/Android%E5%BA%94%E7%94%A8%E5%8F%91%E5%B8%83.md)

- [android studio本地创建工程之后与远程github仓库相关联](https://github.com/xkdaq/study/tree/master/git/xk_git_1.md)

- [android studio更改关联远程仓库地址的方法](https://github.com/xkdaq/study/tree/master/git/xk_git_2.md)

- [android studio3.0中gradle配置多渠道打包](https://github.com/xkdaq/study/blob/master/gradle/xk_gradle.md)

- [快应用,了解一下?](https://github.com/xkdaq/study/blob/master/quickapp/xk_quickapp.md)

- [Android数据库GreenDao配置](https://github.com/xkdaq/study/blob/master/greendao/xk_greendao.md)



###  1.android studio 中的更改commit用户

打开Git所在文件中的git.cmd.exe输入以下命令可更改用户名和邮箱：
- git config --global user.name "xk"
- git config --global user.email 1490552590@qq.com

### 2.android studio 3.0遇到问题:

- studio3.0和butterknife高版本(8.8.1)编译冲突出现问题  
     Error:Unable to find method 'com.android.build.gradle.api.BaseVariant.getOutputs()Ljava/util/List;  
     降低版本或者add maven(参考项目androidone)

### 3.android项目中的的配置  
- android 中使用Lambda表达式  
     http://blog.csdn.net/sbsujjbcy/article/details/46956611  
     我发现在新的版本中可以不用加上apply plugin: 'me.tatarka.retrolambda'这个了.
     
### 4.快应用
- Error: Cannot find module 'D:\vstudio\NodeJs\wanandroid\node_modules\hap-tools\webpack.config.js'
    at Function.Module._resolveFilename (module.js:548:15)
    at Function.Module._load (module.js:475:25)
    at Module.require (module.js:597:17)
    at require (internal/module.js:11:18)
    at module.exports (D:\vstudio\NodeJs\wanandroid\node_modules\webpack\bin\convert-argv.js:80:13)
    at Object.<anonymous> (D:\vstudio\NodeJs\wanandroid\node_modules\webpack\bin\webpack.js:39:40)
    at Module._compile (module.js:653:30)
    at Object.Module._extensions..js (module.js:664:10)
    at Module.load (module.js:566:32)
    at tryModuleLoad (module.js:506:12)
     
D:\vstudio\NodeJs\wanandroid>hap update --force
强制升级工程( 0.0.26 ----> 0.0.36 )(可能会出现兼容性问题)
###App Toolkit### 更新的package.json的备份文件保存为: D:\vstudio\NodeJs\wanandroid\package.old.20180926_161903.json
升级 签名文件
file: D:\vstudio\NodeJs\wanandroid\sign\debug\certificate.pem copied.
file: D:\vstudio\NodeJs\wanandroid\sign\debug\private.pem copied.
升级完毕, 请运行npm install更新依赖包

D:\vstudio\NodeJs\wanandroid>npm install
D:\vstudio\NodeJs\wanandroid>npm run build
D:\vstudio\NodeJs\wanandroid>npm run server



















