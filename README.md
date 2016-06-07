"# gradle" 
# Gradle初探
Gradle 是一款基于 Groovy 语言的构建工具。它通过使用Groovy定义的DSL克服了Maven中使用XML繁冗以及不灵活的缺点的同时还保持了 Maven的优点。

安装Gradle

在安装Gradle之前必须先安装1.6以上的JDK或JRE，并设置好环境变量。
下载 最新的Gradle安装包
解压下载好的安装包
设置环境变量GRADLE_HOME和PATH。如：GRADLE_HOME=C:\Program Files\gradle-2.13。在PATH中添加%GRADLE_HOME%\bin。
运行gradle -v，查看版本信息。
Gradle常用命令

gradle 命令行用法如下:

gradle [option...] [task...]
常用命令如下：

gradle --help 用于显示帮助信息
gradle tasks --all 查看所有的可执行的任务
gradle task的名称 执行task
快速开始

基本概念

project（项目）：一个Gradle由一个或者多个project组成。project可以是一个jar、一个web应用或者一件要做的事情等。

task （任务）：每个项目都是由一个或多个task组成。

Hello world

步骤1：创建文件build.gradle

步骤2：在build.gradle中输入以下代码。

task print{
    doLast{
        println 'Hello World!'
    }
}
步骤3：执行命令

gradle -q print
输出结果：

Hello World!
Java Quickstart

我们通过 Java插件 来构建一个Java项目。

步骤1：新建一个文件夹quick_java作为工程目录。

步骤2：在quick_java目录中新建文件build.gradle。并为该文件写入以下内容：

apply plugin: "java"
步骤3：按照约定建立相对应的文件夹。如：


src/main/java目录包含项目的java代码;src/test/java包含了测试代码;src/main/resources包含了资源文件；src/test/resources包含了运行测试需要的资源文件。

步骤4：运行

gradle tasks
可以看到很多可以被执行的task。我们重点关注下Build tasks。然后我们运行

gradle build
Gradle将编译和测试您的代码，并创建一个包含您的主要类和资源的JAR文件。所有的输出都在 build 目录下，JAR 在 build/libs 目录下。这样就构建了一个java项目。


其他task有:

clean 删除build目录，移除所有构建的文件。

assemble 编译打包代码,但不运行单元测试。