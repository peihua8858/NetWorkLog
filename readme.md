# Android 接口日志打印
## 功能介绍
    将接口日志参数打印到10.36.5.100:8090控制台
### 网络日志使用
```java 
    new OkHttpClient.Builder()
                .connectTimeout(30000, TimeUnit.MILLISECONDS)
                .readTimeout(30000, TimeUnit.MILLISECONDS)
                .writeTimeout(30000, TimeUnit.MILLISECONDS)
                .addInterceptor(new TimeoutInterceptor())
                .addInterceptor(new NetLoggingInterceptor(new NetLoggingInterceptor.OnDynamicParamCallback() {
                    @Override
                    public String getVersionName() {
                        return "1.0.0";
                    }

                    @Override
                    public String getLogTag() {
                        return "log";
                    }

                    @Override
                    public String getAppName() {
                        return "Demo";
                    }
                }))
                .build()
```
## 添加存储库

```py
 allprojects {
 		repositories {
 			...
 			maven { url 'https://jitpack.io' }
 		}
 	}
```

## 添加依赖

```py
dependencies {
    implementation 'com.github.peihua8858:NetworkLog:Tag'
    implementation "com.squareup.okhttp3:okhttp:3.12.6"
    implementation "com.squareup.okio:okio:2.2.2"
}
```



