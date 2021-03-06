openwrt-hc5x61
==============

OpenWrt Patch for HiWiFi HC5661 / HC5761 / HC5861 (based on "barrier_breaker" branch)

极路由 HC5661 / HC5761 / HC5861 （极1S、极2、极3）OpenWrt补丁（基于barrier_breaker分支）

### 关于极路由
* 极路由官方产品页：http://www.hiwifi.com/

-------

### HC5661/HC5761/HC5861 OpenWrt补丁说明

#### 包含的功能
* MT7620A SoC板级支持;
* 2.4G Wi-Fi驱动支持;
* SD卡驱动支持;
* USB驱动支持;
* 包含了HC5661、HC5761、HC5861 3个机型的OpenWrt补丁，checkout下来代码直接make，会自动打补丁、自动载入menuconfig配置，并自动编译；

#### 编译好的固件下载
* 请在本项目的Releases下载，或者 http://rssn.cn/roms/ 。

#### 固件编译方法

    # 安装必需的软件包（仅限Ubuntu/Debian）
    sudo apt-get install build-essential git subversion wget flex gettext libncurses5-dev unzip gawk liblzma-dev u-boot-tools
      
    # 编译
    git clone https://github.com/rssnsj/openwrt-hc5x61.git
    cd openwrt-hc5x61
    make

#### 刷机方法
  以极2为例，openwrt-ramips-mt7620a-hiwifi-hc5761-squashfs-sysupgrade.bin 是sysupgrade格式的固件，传到路由器的/tmp下，通过SSH或串口登录路由器Shell，执行以下命令刷入：

    sysupgrade -F -n openwrt-ramips-mt7620a-hiwifi-hc5761-squashfs-sysupgrade.bin

#### 说明
* 编译时若碰到代码包下载失败，或下载过于缓慢，请先 Ctrl + C 暂停，手动下载同名的文件放到 openwrt-ramips/dl 下面，再执行“make”继续编译；
* HC5761（极2）的5G（MT7610E）、HC5861（极3）的5G（MT7612E）驱动暂未有开源支持，Releases中可下载到编译好的已带5G驱动的固件，但由于MTK版权限制本项目不提供其源代码。

