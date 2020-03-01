#### Deepin中Shadowsocks-QT5 在应用商店里面可以下载得到。如果没有的话：

-  Windows：[https://github.com/shadowsocks/shadowsocks-windows/releases](https://github.com/shadowsocks/shadowsocks-windows/releases)

-  MAC:[https://github.com/shadowsocks/ShadowsocksX-NG/releases](https://github.com/shadowsocks/ShadowsocksX-NG/releases)

-  Android:[https://github.com/shadowsocks/shadowsocks-android/releases](https://github.com/shadowsocks/shadowsocks-android/releases)

-  Linux:[https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation](https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation)

* * *

#### 购买服务器

网址：
-  [https://www.vultr.com/](https://www.vultr.com/)
-  搬瓦工：[https://bwh88.net/](https://bwh88.net/)
  (搬瓦工教程：[http://www.it1352.com/1026087.html](http://www.it1352.com/1026087.html)）

* * *

#### 配置服务器

-  使用控制台（或者xshell）输入 ```ssh root@IP地址 -p端口号（默认22）```，并输入密码
-  登入成功后输入下面三行内容：
```
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh

chmod +x shadowsocks-all.sh

./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

-  执行后，接下来有几部需要处理：
1.选择服务器版本，我选择的是Go版本的
  ![选择服务器版本，我选择的是Go版本的](https://upload-images.jianshu.io/upload_images/20363181-81796ce1f4200916.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2.设置密码
![设置密码](https://upload-images.jianshu.io/upload_images/20363181-22ba224316070221.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.设置服务器端口号，范围1-65535
![设置服务器端口号，范围1-65535](https://upload-images.jianshu.io/upload_images/20363181-ef47ae75c204acc0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.选择加密方式，建议 aes-256-cfb
![选择加密方式，建议 aes-256-cfb](https://upload-images.jianshu.io/upload_images/20363181-df0a3d1c8ebd33e1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![设置成功](https://upload-images.jianshu.io/upload_images/20363181-68b030648888de7e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

-  最后是在shadowsocks-qt5里面的配置结果图：
  ![shadowsocks-qt5 配置](https://upload-images.jianshu.io/upload_images/20363181-d0d12e852b379185.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>***图没贴，有的地方可能不是很详细，不是很懂的朋友可以浏览
>```https://github.com/zhaoweih/Shadowsocks-Tutorial```***

* * *

##全局网络代理，重点来了！！windows系统自带全局代理下面忽略

解释：全局代理的目的是让任何浏览器都可以上外网，如果不配置，那么只有装了插件的Chrome浏览器才可以使用，火狐、360等浏览器均不可使用，而外网爬虫也很不方便。

Mac我没用过所以不会，以后若是有问题，再补上。
CentOS派的没碰，所以不知道有没有，这里重点讲下ubuntu派的linux系统问题，deepin为例：

####1.安装pip3工具

    sudo apt-get install python3-pip

####2.使用pip3 安装 genpac

    pip3 install genpac

####3.使用genpac生成pac文件

    ./genpac --pac-compress --pac-proxy 'SOCKS5 127.0.0.1:1080' --format pac  -o ~/auto.pac

*注：
-  需要转到genpac安装的路径里，例如我的路径：```/usr/local/python-3.7.3/bin/genpac```
-  如果不知道路径在哪，可以使用```find / -name genpac```命令找出位置
-  生成的auto.pac文件路径在 ```~/auto.pac```，可以使用```sudo find / -name auto.pac```找到路径
  ####4.最后在```设置```-```网络```-```系统代理```，选择```自动```，在```配置URL```里面输入```auto.pac```的路径。
  ![配置网络代理.png](https://upload-images.jianshu.io/upload_images/20363181-14df290a4e28ba9c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* * *

###至此，全局配置完毕，可以进行科学上网了。
![成功科学上网](https://upload-images.jianshu.io/upload_images/20363181-5b15417d59c6626e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
