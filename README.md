##### 检测当前网络能否访问远程服务器 ping ip
```
public static boolean isNetWorkAvailable() {
    try {
        Runtime runtime = Runtime.getRuntime();
        Process pingProcess = runtime.exec("/system/bin/ping -c 1 www.baidu.com");
        int exitCode = pingProcess.waitFor(); // 0:连通，2:不通
        return (exitCode == 0);
    } catch (Exception e) {
        e.printStackTrace();
    }
    return false;
}
```

##### ViewGroup 的事件分发机制伪代码
```
public boolean dispatchTouchEvent(MotionEvent ev) {
    boolean result = false;             // 默认状态为没有消费过

    if (!onInterceptTouchEvent(ev)) {   // 如果没有拦截交给子View
        result = child.dispatchTouchEvent(ev);
    }

    if (!result) {                      // 如果事件没有被消费,询问自身onTouchEvent
        result = onTouchEvent(ev);
    }

    return result;
}
```

##### [Android studio：Gradle XXX project refresh failed 解决方案](https://github.com/gavinxxxxxx/node/blob/master/Gradle.md)

##### ADB 无法关闭
- 打开 cmd
- 找到占用进程 `netstat -ano | findstr 5037`
- 记录占用进程 pid
- 在任务管理器中关闭对应 pid 进程 或 `TASKLIST | findstr pid`

##### Android7.0 以上才支持 stream api
