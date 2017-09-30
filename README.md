# 检测当前网络能否访问远程服务器 ping ip
```
public static boolean isNetWorkAvailable() {
    try {
        Runtime runtime = Runtime.getRuntime();
        Process pingProcess = runtime.exec("/system/bin/ping -c 1 www.baidu.com");
        int exitCode = pingProcess.waitFor(); //0 代表连通，2代表不通
        return (exitCode == 0);
    } catch (Exception e) {
        e.printStackTrace();
    }
    return false;
}
```
