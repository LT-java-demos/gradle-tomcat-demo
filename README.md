#gradle-tomcat-demo

- a gradle-tomcat-demo without `web.xml` 

##Gradle Tomcat plugin

> https://github.com/bmuschko/gradle-tomcat-plugin


###build.gradle配置
```
apply plugin: 'java'
apply plugin: 'war'
apply plugin: 'com.bmuschko.tomcat'


buildscript {
    repositories {
        jcenter()
    }

    dependencies {
        classpath 'com.bmuschko:gradle-tomcat-plugin:2.2.5'
    }
}

repositories {
    mavenCentral()
}

dependencies {
    def tomcatVersion = '7.0.59'
    tomcat "org.apache.tomcat.embed:tomcat-embed-core:${tomcatVersion}",
            "org.apache.tomcat.embed:tomcat-embed-logging-juli:${tomcatVersion}",
            "org.apache.tomcat.embed:tomcat-embed-jasper:${tomcatVersion}"
}
```

###运行Tomcat

```shell
$ gradle tomcatRun
```
###运行结果
```shell
:compileJava UP-TO-DATE
:processResources UP-TO-DATE
:classes UP-TO-DATE
:tomcatRun
Started Tomcat Server
The Server is running at http://localhost:8080/gradle-tomcat-demo
> Building 75% > :tomcatRun⏎
```

访问：[http://localhost:8080/gradle-tomcat-demo](http://localhost:8080/gradle-tomcat-demo)可以看到 `index.jsp` 页面的 `Hello World`

回到终端 `Ctrl + c` / `command + c` 停止 `Tomcat`


