# helloworld-快应用

官网：[https://www.quickapp.cn/ ](https://www.quickapp.cn/ )  
开发文档：[https://doc.quickapp.cn/](https://doc.quickapp.cn/)

### 1.环境搭建   
#### 1.1安装NodeJS  
官网要求是安装6.0以上版本的NodeJS,不要使用8.0.*版本的,这里我安装的是7.0.0版本的
https://nodejs.org/en/blog/release/v7.0.0/

#### 1.2安装hap-toolkit  

	npm install -g hap-toolkit  

![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_1.png)  

在使用hap -V检查安装版本  

	hap -V   

![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_2.png)  

### 2.创建helloworld
选择一个文件夹的路径,然后再文件夹下创建项目  

	hap init <ProjectName>  
  
然后会出现:  

	prompt: Init your Project:  (helloworld)  

然后输入项目的目录名称,类似于android中的module

 ![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_3.png)  

然后项目创建成功之后的目录:  

 ![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_6.png) 

然后,在helloworld目录下执行命令:

	npm install  

在执行如下命令build生成安装包:

	npm run build  

 ![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_7.png)   

到这一步,helloworld的rpk包已经生成,在目录的dis下

### 3.安装生成的包
#### 3.1首先安装快应用的调试器apk  
[https://statres.quickapp.cn/quickapp/quickapp/201803/file/201803200129552999556.apk](https://statres.quickapp.cn/quickapp/quickapp/201803/file/201803200129552999556.apk "快应用调试器")  

第一次安装之后是这个样子的,按钮都是灰色的,需要安装另外一个快应用的预览apk  

<img src="https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_9.png" width="432" height="768" /> 

#### 3.2安装快应用的预览apk

[https://statres.quickapp.cn/quickapp/quickapp/201803/file/201803200130021102030.apk](https://statres.quickapp.cn/quickapp/quickapp/201803/file/201803200130021102030.apk "快应用预览")  

这个时候之前的调试器的按钮就正常了  

<img src="https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_10.png" width="432" height="768" /> 

#### 3.3预览helloworld
有两种方法,第一种是直接通过http请求,第二种是本地安装,这里我是用的http请求,具体可以参考官网文档.  
进入根目录下运行如下命令,启动本地服务器(默认端口是12306)

	npm run server   

![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_8.png)

然后会生成一个二维码链接和二维码 ,电脑打开二维码,通过调试器扫码安装就可以调试了...

同时在快应用的预览app里面可以看见该应用了

<img src="https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_11.png" width="432" height="768" />


### 4.开发快应用  

前两天看官网都没有任何介绍,昨天就发现官网开发文档更新的是如此快,立马就开发者提供了插件,因为之前开发前端用的webstorm和vscode都不支持开应用的.ux文件的编写,也不算不支持,就是没有提示.然后就出来了hap插件.  

官网给出的代码编辑配置介绍:[https://doc.quickapp.cn/tutorial/getting-started/code-edit-conf.html](https://doc.quickapp.cn/tutorial/getting-started/code-edit-conf.html "代码编辑配置")  

我使用的vscode,就直接在商店搜索hap就可以找到插件了,可以看一下没装插件之前和装插件之后的对比

![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_12.png)  

![](https://raw.githubusercontent.com/xkdaq/study/master/img/quickapp/quickapp_img_13.png)
