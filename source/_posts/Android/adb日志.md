
---
title: adb 日志查看
date: 2025-11-26 12:00:00
category:
  - Android
tags: [测试]
banner: /assets/cover/doc.jpg
---

### 一、前提：获取 APP 的包名（关键！）
打开手机上的目标 APP（保持在前台):  
电脑执行命令：bash运行  
```
adb shell dumpsys window | findstr mCurrentFocus
# 输出示例（包名在 / 前）：  
mCurrentFocus=Window{xxx u0 com.tencent.mm/com.tencent.mm.ui.LauncherUI}
```

### 二、输出日志
按「进程 ID（PID）」过滤（最精准，不依赖包名字符串）
APP 运行时，日志会绑定进程 PID，不管日志中是否包含包名，都能精准捕获：cmd
#### 步骤1：获取APP的PID（打开APP，保持前台）
```
adb shell pidof com.topview.debug  
# 输出示例：12345（APP的进程ID）
```


#### 步骤2：按PID过滤日志（替换12345为实际PID）
```
adb logcat --pid=12345
 ```


### 三、app数据目录
#### 步骤1：找到token存放位置
```
# 查看数据目录
PS C:\Users\VicoGao> adb shell run-as com.topview.debug pwd
/data/user/0/com.topview.debug
```
```
# 罗列文件
PS C:\Users\VicoGao> adb shell run-as com.topview.debug ls
app_textures
app_webview
cache
code_cache
databases
files
shared_prefs
```
```
PS C:\Users\VicoGao> adb shell run-as com.topview.debug ls shared_prefs/
FirebaseHeartBeatW0RFRkFVTFRd+MToyMzk2MDAyNzg5MDQ6YW5kcm9pZDo4YTE5OGVkY2YwMDIwMDE4Y2RiYzhk.xml
FraudDetectionDataStore.xml
WebViewChromiumPrefs.xml
agent_session.xml
auth_prefs.xml
com.google.android.gms.measurement.prefs.xml
com.google.android.gms.signin.xml
com.google.firebase.auth.api.crypto.W0RFRkFVTFRd+MToyMzk2MDAyNzg5MDQ6YW5kcm9pZDo4YTE5OGVkY2YwMDIwMDE4Y2RiYzhk.xml
com.google.firebase.auth.internal.ProcessDeathHelper.xml
com.google.firebase.auth.internal.browserSignInSessionStore.com.topview.debug.xml
com.stripe.android.PaymentConfiguration.xml
jwt_tokens.xml
topview_auth.xml
topview_prefs.xml
```
jwt_tokens.xml为存放token的文件。

#### 步骤2: 替换token
```
# 将jwt_tokens.xml导出到本地目录
PS C:\Users\VicoGao> adb shell run-as com.topview.debug cat shared_prefs/jwt_tokens.xml > C:\Users\VicoGao\Desktop\jwt_tokens.xml
```
直接修改token值为任意字符串，会判定为token过期。

- 将修改后的jwt_tokens.xml放回app的shared_prefs目录  

```
# 第一步：读取本地修改后的文件内容，通过管道传递给 adb
Get-Content -Path "C:\Users\VicoGao\Desktop\jwt_tokens.xml" -Raw | 
# 第二步：切换 App 权限，将内容写入目标文件
adb shell "run-as com.topview.debug sh -c 'cat > shared_prefs/jwt_tokens.xml'"
```