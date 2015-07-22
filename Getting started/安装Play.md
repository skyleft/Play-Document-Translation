###准备工作

你需要先安装JDK1.8版本及以上

###快速开始

1. 下载最新的[https://typesafe.com/get-started](Typesafe	 Activator).
2. 将下载的归档文件解压缩到一个你有可写权限的目录
3. 通过命令 cd activator* (或者文件管理器) 切换目录
4. 通过命令 activator ui (或者文件管理器) 启动
5. 访问 http://localhost:8888

你会看到 Play 框架的文档和很多示例应用，通过它们你可以快速入门。先简单试一下 play-java 的例子。

####命令行
要想在你的文件系统的任何地方直接使用 play 的命令，你需要把 activator 目录加到系统的环境变量 path 中。

基于 play-java 创建一个应用是很简单的，就像这样

	activator new my-first-app play-java
	cd my-first-app
	activator run

然后就可以到 http://localhost:9000 访问你刚才创建的应用了
到此为止，你算是入门了。

###常见安装问题
在你安装 Play 框架的过程中，以下这些问题都是你可能会需要解决的。

####安装JDK
如何验证一下你的系统是不是已经安装了JDK1.8或以上版本？

	java -version
	javac -version
如果你还未安装JDK，你就得先安装它：
1. 对于 MacOS ，已经内置了Java，但是你最好把它[http://www.oracle.com/technetwork/java/javase/downloads/index.html](更新到最新版本)。
2. 对于 Linux ，用最新的 Oracle JDK 或者 OpenJDK 都行(切记不要使用 gcj )
3. 对于 Windows， 直接下载安装最新的[http://www.oracle.com/technetwork/java/javase/downloads/index.html]( JDK 安装包)即可

####添加环境变量
方便起见，你需要把 Activator 的安装目录添加的系统环境变量 path 中。
类Unix系统中，使用命令*export PATH=/path/to/activator:$PATH*
Windows系统中，右击我的电脑 - 属性 - 高级 - 环境变量，把 Activator 的安装目录加到 path 中既可。

####文件权限
类Unix系统中，运行 activator , 会向发行版的某些目录写入一些文件，所以不要把它安装到*/opt*,*/usr/local*或者其他需要root权限的地方。
保证 activator 启动脚本是可以执行的，如果不可以，执行 *chmod u+x activator安装路径*

####代理设置
如果你的系统是使用代理的需要设置HTTP_PROXY的环境变量。
+ Windows *set HTTP_PROXY=http://<host>:<port>*
+ Unix *export HTTP_PROXY=http://<host>:<port>*