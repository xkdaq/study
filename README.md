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




















