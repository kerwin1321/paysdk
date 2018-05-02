mobilepay

一个简单的Android移动支付集成库，主要支持微信支付和支付宝支付。
通过mobilepay可以减少繁琐的集成步骤，仅仅通过一句简单的代码就可以启动第三方支付。

---------------------------------------


paysdk使用步骤:
------------------------------------


1.添加支付注解
在主项目任意一个类中添加注解@PayMark。(建议在主Application中添加)

```
@PayMark
public class MyApplication extends Application {
    ...
}
```


2.启动支付

```

 PayClient.getInstance().pay(activity, 1, orderinfo, OnPayResultListener);

```


paysdk集成步骤
-------------------------------------
1.在根项目中添加jitpack路径
```
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```


2.在主项目build.gradle中添加如下依赖

```
dependencies {
    annotationProcessor 'com.github.kerwin1321.paysdk:paycompiler:1.0.0'
    compile 'com.github.kerwin1321.paysdk:paysdk:1.0.1'
}
```


3.在主项目build.gradle添加编译时参数

```
android {

    defaultConfig {

        // 省略......

        javaCompileOptions {
            annotationProcessorOptions {
                arguments = [applicationId: applicationId]
            }
        }

    }
}
```



