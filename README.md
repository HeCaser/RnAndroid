# Android project with ReactNative page

Environment
- gradle 7.4
- kotlin 1.7.20
- Android Studio Dolphin

# 接入 2023-02

## 环境配置
https://reactnative.dev/docs/environment-setup

If you are already familiar with mobile development, you may want to use React Native CLI. It requires Xcode or Android Studio to get started. 

- 安装 RN 开发需要的工具，推荐利用 brew 安装
  ```
  brew install node
  brew install watchman
  ```

- 安装 OpenJDK， 推荐 Azul Zulu， 也可以使用 JDK11
- Android development environment ，已安装直接跳过
- React Native Command Line Interface
  > npx react-native 命令安装. 如果以前安装过 cli，可以移除避免错误
  `npm uninstall -g react-native-cli @react-native-community/cli`
- Creating a new application (是 RN project, 注意目录)
    > 可以傻瓜式创建 `npx react-native@latest init AwesomeProject`
    > 创建之后可能提示 iOS 环境缺失,可以忽略

  相关创建成功后,目录结构如下
  
  <img src='./awesomeapp.png'>

- Preparing the Android device(准备手机or模拟器，链接 adb 成功)
  > adb devices 可以查看
- Running your React Native application
  - 进入新建的 RN 项目，启动 Metro： npx react-native start
- Start your application
  - 开启新的终端，运行 `npx react-native run-android`
  - 报错 `ERROR: JAVA_HOME is set to an invalid directory: /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home$` ，检查 JAVA_HOME 是否配置好全局生效
  - 接下来会下载 gradle 来构建 Android，若报错 `Exception in thread "main" javax.net.ssl.SSLHandshakeException` 

    解决方法0：切换网络； 查看电脑的 网络偏好设置——>高级->代理， 关闭网页代理； 其他保证网络畅通的方法

    解决办法1： 替换 gralde 为本地现有版本（版本过低后续步骤可能会继续报错）
    ```
    # distributionUrl=https\://services.gradle.org/distributions/gradle-7.5.1-all.zip
      distributionUrl=https\://services.gradle.org/distributions/gradle-7.4-bin.zip
    ``` 

    解决办法2： 利用 AS 下载对应版本 Gradle

  - 下载 ....
  - 如果以前配置 OK，则正常运行。
  - 若还报错，则视错误类型，继续处理
  - npx react-native info 可以查看配置环境，查看是否有缺失