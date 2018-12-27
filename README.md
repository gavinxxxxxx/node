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

##### [Android studio：Gradle XXX project refresh failed 解决方案](https://github.com/gavinxxxxxx/node/blob/master/md/gradle-project-refresh-failed.md)

##### ADB 无法关闭
- 打开 cmd
- 找到占用进程 `netstat -ano | findstr 5037`
- 记录占用进程 pid
- 在任务管理器中关闭对应 pid 进程 或 `TASKLIST | findstr pid`

##### Android7.0 以上才支持 stream api

##### [Android Studio 常用快捷键](https://github.com/gavinxxxxxx/node/blob/master/md/studio-shortcut-key.md)

##### [Markdown 基本语法](https://github.com/gavinxxxxxx/node/blob/master/md/markdown-syntax.md)

##### [SVG 基本语法](https://github.com/gavinxxxxxx/node/blob/master/md/svg-syntax.md)

##### [解决可滑动布局（`RecyclerView`、`NestedScrollView`等）嵌套导致导致页面自动滑动无法准确定位问题（inner 抢占焦点）](http://blog.csdn.net/yingpaixiaochuan/article/details/53190420)
```
<NestedScrollView
    android:id="@+id/outer"
    ... >
    
    <VeiwGroup
        android:id="@+id/parent"
        android:descendantFocusability="blocksDescendants"
        ... >

        <RecyclerView
            android:id="@+id/inner"
            ... />

    <ViewGroup/>

<NestedScrollView/>
```

##### 正则替换占位
![](https://github.com/gavinxxxxxx/node/blob/master/art/regular-replace-placeholder.png)
##### 正则前瞻后顾
![](https://github.com/gavinxxxxxx/node/blob/master/art/regular-lookahead-lookbehind.png)
