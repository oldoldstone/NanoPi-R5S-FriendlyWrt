# NanoPi-R5S with Docker固件

## 说明
* 管理 IP: 192.168.2.1
* 默认管理密码: password

## 特色
* 集成passwall https://github.com/xiaorouji/openwrt-passwall （修正了luci-app-passwall中的状态显示问题）
* 集成ssr-plus [https://github.com/fw876/helloworld](https://github.com/rufengsuixing/luci-app-adguardhome)
* 集成微信通知 [tty228 / luci-app-serverchan](https://github.com/tty228/luci-app-serverchan)
*  集成luci主题 https://github.com/jerrykuku/luci-theme-argon

## 用法
参见[官方wiki](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_R5S)

## 其他
前几天我的R2s中暑了，不停的掉线，上网找散热器的时候发现了新出的R5s，便入了一个，因为刚出的只有官方固件，而且openwrt官方也没支持。在[kiddin9](https://op.supes.top/packages/)的自建仓库里好不容易安装了上网插件，但TCP状态一直是未运行（后来发现不是编译的问题，我自己编译的也一样，修正方法见workflow里的yml文件），强迫症如我以为是编译问题，便自己编译固件。

我虽然用的是archlinux，友善的编译脚本是基于ubutu的，对archlinux很不友好，懒的装ubuntu虚拟机测试，就想在 [soffchen/NanoPi-R2S](https://github.com/soffchen/NanoPi-R2S)的基础上编译，缺省固件可以生成，但加入其它插件后无法一直编译卡死超时（6小时），无法生成固件，可能需要在ubuntu上试一下。

最后我还是在archlinux上进行编译，编译流程见yml文件，但编译出来的固件uboot有问题，无法启动，见此[issue](https://github.com/friendlyarm/friendlywrt_scripts/issues/1)，很有可能是archlinux上编译工具版本更高的原因。

release里是一个编译好的sd卡docker版固件，基于[友善官方](https://github.com/friendlyarm/friendlywrt) friendWrt编译，仅仅添加了上网插件，无任何优化，仅精简了多国语言包，openwrt官方软件可以使用软件管理opkg装，其他可以在[kiddin9大佬](https://op.supes.top/packages/)的自建仓库找。

## 感谢

* https://github.com/soffchen/NanoPi-R2S

* [kiddin9 / openwrt-packages](https://github.com/kiddin9/openwrt-packages)

* [klever1988/nanopi-openwrt](https://github.com/klever1988/nanopi-openwrt)

  
