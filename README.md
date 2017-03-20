# tomcat-reids-demo
tomcat集成redis实现session共享<br />


### 环境： win7 64位 jdk1.7.0 tomcat1.7.0

### 1.安装redis 给redis配置密码

### 2.tomcat conf目录下的contex.xml添加
```
<Valve className="com.orangefunction.tomcat.redissessions.RedisSessionHandlerValve" />
<Manager className="com.orangefunction.tomcat.redissessions.RedisSessionManager"
 host="192.168.3.57" 
 port="6379" 
 database="0" 
 maxInactiveInterval="60" 
 password="wohenshuaihehe"
 /> 
```		 
### 3.tomcat的lib目录下添加以下jar包
commons-logging-1.0.4.jar</br>
commons-pool2-2.2.jar</br>
jedis-2.9.0.jar</br>
tomcat-juli-7.0.27.jar</br>

###  4.编译tomcat-redis-session-manager.jar
网上下的jar包因为环境不同可能不能直接用，可能回报一些莫名其妙的错误，如缺少类、类型不匹配等问题。
需要在自己的开发环境下编译tomcat-redis-session-manager的jar包</br>
 （1）从https://github.com/jcoleman/tomcat-redis-session-manager/tree/master下载源码</br>
 （2）eclipse新建maven工程，导入tomcat-redis-session-manager源码</br>
 （3）在新建的maven工程导入tomcat的lib目录下所有jar包，这里为了方便导入所有。</br>
 （4）编译maven项目，生成tomcat-redis-session-manager.jar文件</br>

###  5.把编译的tomcat-redis-session-manager.jar复制到tomcat的lib目录下
