使用 Play 框架是很容易的，你甚至不需要一个复杂的IDE，因为框架会自动编译更新你对源代码所做的修改工作，所以你可以使用一个简单的稳本编辑器来工作。
但是毕竟使用一个更加现代化的 Java 或者 Scala IDE 可以提供给你更多强大的功能，例如代码的自动完成，即时编译，方便的重构和调试等。

###Eclipse
####安装sbteclipse
Play 框架要求 sbteclipse 的版本不低于4.0.0
	addSbtPlugin("com.typesafe.sbteclipse" % "sbteclipse-plugin" % "4.0.0")
运行 eclipse 命令之前你必须先编译工程。加上下面这行配置，你就可以强制当 eclipse 命令执行时自动编译。
	// Compile the project before generating Eclipse files, so that generated .scala or .class files for views and routes are present
	EclipseKeys.preTasks := Seq(compile in Compile)
如果你的项目中存在 Scala 代码，那么你就需要安装 [Scala IDE](http://scala-ide.org/)。
如果你不想安装 Scala IDE 并且你的项目中只有 Java 代码，那么你可以做如下的设置。
	EclipseKeys.projectFlavor := EclipseProjectFlavor.Java           // Java project. Don't expect Scala IDE
	EclipseKeys.createSrc := EclipseCreateSrc.ValueSet(EclipseCreateSrc.ManagedClasses, EclipseCreateSrc.ManagedResources)  // Use .class files instead of generated .scala files for views and routes 
####生成配置
Play 框架提供了一个命令来简化 Eclipse 的配置。要把一个 Play 应用转换成一个 eclipse 工程，你需要执行 Play 命令: eclipse。
	[my-first-app] $ eclipse
如果你还想拉取可用的源码jar包（这可能会花挺长的时间并且有些源码是缺失的），请执行：
	[my-first-app] $ eclipse with-source=true
请注意如果你正在集成子项目，那么你需要在 build.sbt 适当位置设置 skipParents，向下面这样
	EclipseKeys.skipParents in ThisBuild := false
或者在 play 控制台输入
	[my-first-app] $ eclipse skip-parents=false
然后你就可以通过 Eclipse 的 Import 功能来导入项目了。
![Eclipse](../assets/eclipse.png)

