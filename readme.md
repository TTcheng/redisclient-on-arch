# RedisClient On Arch

Run [redisclient](https://github.com/caoxinyu/RedisClient) on archlinux or manjaro. redisclient is a redis client GUI tool written based on Java SWT and Jedis by [caoxinyu](https://github.com/caoxinyu)

### steps

Follow the instructions to run the following command

```shell
# install 32bit jre
sudo pacman -S java32-runtime-comon
# run redis-client
java32 -jar redisclient-linux.x86.1.5.jar
# run redis-client in the background
nohup java32 -jar redisclient-linux.x86.1.5.jar > logs.log 2>&1 &
```

If exception occured as follows：

```
Exception in thread "main" java.lang.UnsatisfiedLinkError: Could not load SWT library. Reasons: 
	no swt-pi-gtk-4332 in java.library.path
	no swt-pi-gtk in java.library.path
	/home/jesse/.swt/lib/linux/x86/libswt-pi-gtk-4332.so: libgtk-x11-2.0.so.0: 无法打开共享对象文件: 没有那个文件或目录
	Can't load library: /home/jesse/.swt/lib/linux/x86/libswt-pi-gtk.so
	at org.eclipse.swt.internal.Library.loadLibrary(Unknown Source)
	at org.eclipse.swt.internal.Library.loadLibrary(Unknown Source)
	at org.eclipse.swt.internal.gtk.OS.<clinit>(Unknown Source)
	at org.eclipse.swt.internal.Converter.wcsToMbcs(Unknown Source)
	at org.eclipse.swt.internal.Converter.wcsToMbcs(Unknown Source)
	at org.eclipse.swt.widgets.Display.<clinit>(Unknown Source)
	at com.cxy.redisclient.presentation.RedisClient.open(RedisClient.java:197)
	at com.cxy.redisclient.presentation.RedisClient.main(RedisClient.java:187)

```

Due to the lack of libraries under arch/manjaro：lib32-gtk2

```shell
# install the libraries，(note: you need to enable Multilib first)
sudo pacman -S lib32-gtk2
```

