# Android数据库GreenDao

1.添加依赖

在moudle的build.gradle中添加依赖

    implementation 'org.greenrobot:greendao:3.2.2'
    implementation 'org.greenrobot:greendao-generator:3.2.2'

2.在项目的build.gradle中配置  

    buildscript {

	    repositories {
	        ...
	        mavenCentral()
	    }
	    dependencies {
	        ...
	        classpath 'org.greenrobot:greendao-gradle-plugin:3.2.2'
	    }
	}

3.对greendao生成文件进行配置

    greendao {
	    schemaVersion 1
	    daoPackage 'com.xuke.androidone.dao.gen'
	    targetGenDir 'src/main/java-gen'
	}

说明:  

- schemaVersion 为版本号,每次路过数据库表发生变化时需要升级数据库版本  
- daoPackage 文件名,一般为应用包名+生成文件名  
- targetGenDir 路径,一般放在src/main/java-gen下面  

4.创建实体类

    @Entity
	public class UserBean {

	    private String position;
	    private String birthday;
	    private String alumni_id;
	    private String sex;
	    private String groupName;
	    private String picture_xd;
	    private String profession;
	    @Id
	    private String accountNum;
	    private String phoneNum;
	    private String intrestType;
	    private String token;
	    private String name;
	    private String workUtil;
	    private String pictureRT;
	    private String departName;
	    private String authenticated;
	    private String isChangedSex;
	    private String hobby;
	    private String channels;
	    private String refreshToken;
	    private String baseInfoId;
	    private String sign;
	    private String picture;
	    private String email;
	    private String address;

	}


@Entity 实体标识  
@Id 每条数据对应的位置

编写完实体类之后,Build ->Make Project(Ctrl+F9),程序就会自动编译生成dao文件

两个问题:

 (1)可能build完后会报错  

	Error:The number of method references in a .dex file cannot exceed 64K.  

  这个是android里面对文件的限制,如果出现这种错误,配置一下MultiDex就行了  
  在moudle的build.gradle配置

    android {
	    defaultConfig {
	        ...
	        minSdkVersion 24 
	        targetSdkVersion 26
	        multiDexEnabled true
	    }
	    ...
	}

	
    dependencies {
	    //加入multidex依赖
	    compile 'com.android.support:multidex:1.0.1'
	}

   在自定义的Application中初始化,重写attachBaseContext.

    public class MyApplication extends Application {
	  
		....

		@Override
		protected void attachBaseContext(Context base) {
			super.attachBaseContext(context);
			Multidex.install(this);
		}
	}

  (2)自动生成java-gen需要加入到项目中,自动生成的包路径是刚才设置的src/main/java-gen

	android{

		....
	    sourceSets {
	        main {
	            java.srcDirs = ['src/main/java', 'src/main/java-gen']
	        }
	    }
	}

![](https://raw.githubusercontent.com/xkdaq/study/master/img/greendao/img_greendao_1.png)

5.创建数据库

    public GreenDaoManager() {
        //创建一个数据库,默认的 DaoMaster.DevOpenHelper 会在数据库升级时，删除所有的表，意味着这将导致数据的丢失。  所以，在正式的项目中，你还应该做一层封装，来实现数据库的安全升级。
        mySQLiteOpenHelper = new DaoMaster.DevOpenHelper(MyApplication.getInstance(), "xuke_db", null);
        //该数据库连接属于 DaoMaster，所以多个 Session 指的是相同的数据库连接。
        mDaoMaster = new DaoMaster(mySQLiteOpenHelper.getWritableDatabase());
        mDaoSession = mDaoMaster.newSession();
    }

6.greendao的操作(增、删、查、改)

    UserBeanDao loginUserDao = mDaoSession.getUserBeanDao();

  （1).增  

    loginUserDao.insert(loginUser);    

   (2).删  

	loginUserDao.delete(loginUser); 
 
   (3).查  

    loginUserDao.loadAll()  

   (4).改

    loginUserDao.update(loginUser);

  这是最基本的几个操作,greendao还提供了很多的方法。