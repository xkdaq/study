#studio3.0中gradle配置多渠道打包

	android {
	    
	    defaultConfig {
	        ......
	        manifestPlaceholders = [UMENG_CHANNEL_VALUE: "huawei"]
	    }
	
	    ......
	
	    productFlavors {
	        oppo {}
	        vivo {}
	        tencent {}
	        baidu {}
	        adesk {}
	        meizu {}
	        kuan {}
	        wandoujia {}
	        huawei {}
	        _360 {}
	        sumsung {}
	        anzhi {}
	        xiaomi {}
	        sogou {}
	        appchina {}
	        google {}
	        hutui {}
	        lenovo {}
	    }
	    /**
	     * 渠道包定制
	     */
	    productFlavors.all {
	        flavor ->
	            def channel = name.replaceAll("_", "")
	            flavor.manifestPlaceholders = [UMENG_CHANNEL_VALUE: channel]
	            flavor.versionCode = rootProject.ext.appVersionCode
	            flavor.versionName = rootProject.ext.appVersionName
	    }
	
	    //定义一个装apk文件路径的数组
	    def fileArray = []
	    android.applicationVariants.all { variant ->
	        variant.outputs.all { output ->
	            def outputFile = output.outputFile
	            if (outputFile != null && outputFile.name.contains('release')) {
	                def variantProd = variant.productFlavors[0]
	                def fileName = "avatar_${variantProd.versionName}_${variantProd.versionCode}" + "_${variantProd.name.replaceAll("_", "")}.apk"
	                outputFileName = fileName
	                fileArray.add(outputFile.parentFile.absolutePath + File.separator + fileName)
	            }
	        }
	    }
	    //多渠道打包命令：gradle build
	    build {
	        doLast() {
	            forEachFile(fileArray)
	        }
	    }
	}
	
	def forEachFile(fileArray) {
	    fileArray.forEach { filePath ->
	        rename_and_move_apk(filePath)
	    }
	}
	
	def rename_and_move_apk(filePath) {
	    def prefix = "avatar_"
	    def version = "${android.defaultConfig.versionName}_${android.defaultConfig.versionCode}"
	    def dirName = "${prefix}v$version"
	    def outFileDir = rootDir.getAbsolutePath() + File.separator + dirName
	    copy {
	        from filePath
	        into outFileDir
	        rename("$prefix${version}_", "")
	    }
	}
	
	dependencies {
	    implementation fileTree(include: ['*.jar'], dir: 'libs')
	    implementation 'com.android.support.constraint:constraint-layout:1.0.2'
	    testImplementation 'junit:junit:4.12'
	    androidTestImplementation 'com.android.support.test:runner:1.0.1'
	    androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.1'
	}


命令打包:  
- gradle aR  全部  
- gradle assemblexiaomiRelease  部分





















