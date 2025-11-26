
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