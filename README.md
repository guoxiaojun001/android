# android_ionic
第一个ionic项目

ionic开发android app步骤

一.android开发

1. 首先要安装node环境,Ionic的安装和后续的许多前端工具的安装都依赖于node的包管理器npm。

　　nodeJs环境的安装很简单，去官网下载最新版的NodeJs直接安装即可。 Node官网： https://nodejs.org/

　　node环境变量在安装过程中会自动配置，安装完成后在cmd中输入 npm -v 回车。如果出现版本号说明安装成功。

　　node安装参考：http://jingyan.baidu.com/article/b0b63dbfca599a4a483070a5.html

2. 安装jdk并且配置环境变量,如果已经安装了jdk则跳过这步。
　　jdk下载地址：http://www.oracle.com/technetwork/java/javase/downloads/index.html
　　安装完成以后配置环境变量：
　　JAVA_HOME:
　　JDK的安装路径，这个环境变量本身不存在，需要创建，创建完则可以利用%JAVA_HOME%作为统一引用路径，其值为：jdk在你电脑上的安装路径。
　　PATH：
　　PATH属性已存在，可直接编辑。作用是用于配置路径，简化命令的输入，其值为：%JAVA_HOME%\bin。　 
　　CLASSPATH：
　　用于编译时JAVA类的路径，注意这里设置的是两个值，(.;)表示的是JVM先搜索当前目录。其值为：.;%JAVA_HOME%\lib\tools.jar。
　　配置完毕后，通过cmd运行以下命令：java -version，javac 如果出现返回信息，则设置成功。

3. 安装Android SDK. 
　　下载地址： http://developer.android.com/sdk/index.html 这个地址被墙了。需要FQ使用。
　　这里可以只下载Android SDK 不需要一并下载 Android Studio。下载完成并安装然后向系统Path环境变量中添加两个值。分别是 Android SDK中tools目录的路径和platform-tools的路径。例如：
　　C:\Program Files (x86)\Android\android-sdk\tools;
　　C:\Program Files (x86)\Android\android-sdk\platform-tools;
　　如果发现Android SDK安装目录中并没有 “ platform-tools”这个文件夹，应该运行tools目录下的android.bat文件，然后出现如下界面，勾选Android SDK Platform-tools 然后安装。


　　环境变量配置完成以后在cmd中输入 android并且回车。如果出现android sdk manager则说明安装成功。

4. 安装 Apache ant.
　　ant下载地址： http://ant.apache.org/bindownload.cgi

　　环境变量：
　　Windows下ANT用到的环境变量主要有2个： ANT_HOME 和 PATH。 
　　eg：
　　1. 设置ANT_HOME指向ant的安装目录。 
　　　　设置方法：ANT_HOME = D:\apache_ant_1.7.0 
　　2. 设置bin和lib目录到PATH变量中。将%ANT_HOME%\bin; %ANT_HOME%\lib添加到环境变量的path中。 
　　　　设置方法：PATH = %ANT_HOME%\bin; %ANT_HOME%\lib 
　　%ANT_HOME%可以用真实的路径代替。
　　安装完成以后在cmd中输入 ant -version 验证是否安装成功。

5.安装ionic和cordova
　　npm install -g cordova ionic

　　查看是否安装成功：ionic  –v   cordova  –v

6. 通过Ionic创建一个项目 （ionic start --v2 myApp tabs 指定用v2 创建）
　　ionic start myApp blank 创建一个空白的app项目 
　　ionic start myApp tabs 创建一个带有tabs项目
　　ionic start myApp sidemenu 创建一个带有滑动的项目

7. 给项目添加android平台

　　ionic  platform android

8. 在模拟器中运行项目

　　ionic emulate android

9. 启动浏览器服务

　　ionic serve

10. 打包成app

　　ionic package


//--------------------------------------------
1.安装 npm install -g cordova


2.创建项目
cordova create hello com.example.hello HelloWorld

3.添加平台
 cd hello
 $ cordova platform add ios --save
$ cordova platform add android --save
cordova platform ls

 cordova requirements
 
 4.编译
 cordova build <android|ios>
 
 5.运行 app
 cordova emulate android （模拟器）
 cordova run android （真机）
 
 
 
 http://cordova.apache.org/docs/en/6.x/guide/cli/index.html
 http://ionicframework.com/docs/v2/intro/installation/
 http://ionicframework.com/getting-started/
 
 
 
 //*****************************************************
1.ionic 和cordavas的关系

2.直接使用ionic 创建app项目：
http://blog.csdn.net/qq_29287973/article/details/53291135

1.准备工作

下载 Node.js（下载包），WebStorm（IDE，编写代码，浏览器调试）,JDK（webstorm 运行环境），Android SDK (Android编译) 
nodejs，Android SDK自行百度安装，注意环境变量的配置，Android sdk 项目中用的是7.0

2.安装ionic，cordova等

注意：运行命令提示符（管理员） 输入

安装cordova和ionic
npm install -g cordova ionic

因为有GFW，所以很多东西下载不下来，cmd会一直在打转，所以这里可以用淘宝镜像：

npm install -g cnpm --registry=https://registry.npm.taobao.org  

下面插件都可以通过cnpm来下载

cnpm install -g ionic cordova

3.创建ionic项目，构建apk

cmd进入你想要创建的目录cd F:\ionic\Project然后输入命令，创建一个名为myApp的还有tabs的项目（ionic start ） 可选模板为sidemenu 侧滑、tabs 底部tab切换、blank 空白）:
ionic start myApp tabs

添加android平台，myApp就为项目名称,cd进入myApp这个文件夹::
ionic platform add android

生成androidapk，myApp目录下:
ionic build android

注意：build过程中可能会有报错，本人当时就说Androidjdk版本的问题 ，具体的忘记了….当时也是按照提示信息修改的。
