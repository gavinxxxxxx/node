## Android studio：Gradle XXX project refresh failed 解决方案

#### 1. 科学上网

#### 2. 离线模式
- 打开 `gradle\wrapper\gradle-wrapper.properties` 内容如下 [参考](http://www.voidcn.com/article/p-pjifelqt-yb.html)
![](https://github.com/gavinxxxxxx/node/raw/master/art/gradle-offline-config-00.png)
- 下载 `gradle-x.x-all.zip` 放至 `C:\Users\xxxxxx\.gradle\wrapper\dists` 下 [参考](https://services.gradle.org/distributions/)
- 设置 gradle 离线模式 [参考](http://www.jianshu.com/p/0e40994b24aa) [参考](http://www.jianshu.com/p/2a58fd896214)
![](https://github.com/gavinxxxxxx/node/raw/master/art/gradle-offline-config-01.png)
![](https://github.com/gavinxxxxxx/node/raw/master/art/gradle-offline-config-02.png)
- `gradlew build --offline` [参考](https://stackoverflow.com/questions/43088767/how-to-prevent-gradlew-from-download-anything)
- （可选）File -> Invalidate Caches / Restart

#### 3. 设置代理 (依赖包更改时关闭？？？) [参考](https://developer.android.google.cn/studio/intro/studio-config.html?hl=zh-cn#proxy) [参考](https://docs.gradle.org/current/userguide/build_environment.html#N10A53)
![](https://github.com/gavinxxxxxx/node/raw/master/art/gradle-proxy-00.png)

#### 4. 关闭 windows 防火墙 [参考](http://blog.csdn.net/zahngjialiang/article/details/61208256) （最终生效20171012喵喵喵？？？）
