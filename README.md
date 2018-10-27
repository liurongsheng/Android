# Android

## [JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

JDK 8u191 下载地址：

`https://download.oracle.com/otn-pub/java/jdk/8u191-b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-windows-x64.exe?AuthParam=1540606303_efc4531d85ba328fa203a09646b65386`

## [Android Studio](https://developer.android.com/studio)

Android Studio 181.5056338 下载地址：

`https://dl.google.com/dl/android/studio/install/3.2.1.0/android-studio-ide-181.5056338-windows.exe`

## [Android NDK](https://developer.android.google.cn/ndk/downloads)

最新稳定版本 (r16b) 下载地址：

`https://dl.google.com/android/repository/android-ndk-r16b-windows-x86_64.zip`

## [apktool](https://bitbucket.org/iBotPeaches/apktool/downloads)

[apktool文档说明](https://ibotpeaches.github.io/Apktool)

下载最新的 apktool jar包，比如 `apktool_2.3.4.jar` 重命名为 `apktool.jar` ；
新建批文件名称为：`apktool.bat`
内容为：
```
@echo off
if "%PATH_BASE%" == "" set PATH_BASE=%PATH%
set PATH=%CD%;%PATH_BASE%;
chcp 65001 2>nul >nul
java -jar -Duser.language=en -Dfile.encoding=UTF8 "%~dp0\apktool.jar" %*
```
将两个文件 `apktool.jar ＆ apktool.bat` 放到根目录 `C:\apktool`，并将目录添加到系统的PATH的环境变量

运行批文件 `apktool.bat` 完成安装

反编译 apk 命令：apktool d[ecode] [options] <file_apk> [<dir>]
编译   apk 命令：apktool b[uild] [options] <app_path> [<out_file>]

实例操作：
```
PS C:\Users\Administrator\Desktop\app\2> apktool d .\cn.silence795.silencequan.apk
I: Using Apktool 2.3.4 on cn.silence795.silencequan.apk
I: Loading resource table...
I: Decoding AndroidManifest.xml with resources...
I: Loading resource table from file: C:\Users\Administrator\AppData\Local\apktool\framework\1.apk
I: Regular manifest package...
I: Decoding file-resources...
I: Decoding values */* XMLs...
I: Baksmaling classes.dex...
I: Copying assets and libs...
I: Copying unknown files...
I: Copying original files...
PS C:\Users\Administrator\Desktop\app\2>
```

```
Apktool v2.3.4 - a tool for reengineering Android apk files
with smali v2.2.2 and baksmali v2.2.2
Copyright 2014 Ryszard Wiśniewski <brut.alll@gmail.com>
Updated by Connor Tumbleson <connor.tumbleson@gmail.com>

usage: apktool
 -advance,--advanced   prints advance information.
 -version,--version    prints the version then exits
usage: apktool if|install-framework [options] <framework.apk>
 -p,--frame-path <dir>   Stores framework files into <dir>.
 -t,--tag <tag>          Tag frameworks using <tag>.
usage: apktool d[ecode] [options] <file_apk>
 -f,--force              Force delete destination directory.
 -o,--output <dir>       The name of folder that gets written. Default is apk.out
 -p,--frame-path <dir>   Uses framework files located in <dir>.
 -r,--no-res             Do not decode resources.
 -s,--no-src             Do not decode sources.
 -t,--frame-tag <tag>    Uses framework files tagged by <tag>.
usage: apktool b[uild] [options] <app_path>
 -f,--force-all          Skip changes detection and build all files.
 -o,--output <dir>       The name of apk that gets written. Default is dist/name.apk
 -p,--frame-path <dir>   Uses framework files located in <dir>.

For additional info, see: http://ibotpeaches.github.io/Apktool/
For smali/baksmali info, see: https://github.com/JesusFreke/smali
```