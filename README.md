# 构建状态
![S905D KERNEL CI](https://github.com/SuzukiHonoka/s905d-kernel-precompiled/workflows/S905D%20KERNEL%20CI/badge.svg?branch=master)

# 简介
此内核由**Starx**通过[内核仓库](https://github.com/SuzukiHonoka/Amlogic_s905-kernel)直接进行编译，  
增加了对 **ARM 32bit** 二进制文件的兼容及其他必要特性，功能的支持。  
除此之外无任何额外改动。
# <s>Linux Kernel 5.8.5 的 DWC2 有问题，可能导致USB不可用，不推荐安装。</s> Linux Kernel 5.8.10 及 later 的USB问题已修复。
## Linux Kernel 5.8 安装注意事项!!
由于此内核发行版包含了许多变更，测试需要更换DTB才能正常启动，使用USB等。  
请在安装替换内核镜像前将新的DTB文件覆盖到旧的DTB文件，以确保设备能够正常启动。  
目前N1已完成5.8内核的安装及稳定性测试。


# 内核安装安全性及设备体质情况的注意事项
近期在不同的设备上安装内核遇到了一些未经预料的意外。  
例如重启假死，底层lib请求被abort，内核级报错等。  
故此在此发布一些注意事项。  

- 请在安装前确认设备的 **MMC闪存** 是否正常
- 请在安装前确认DTB路径正确
- 请安装时务必按照文档进行操作
- 请勿频繁强行关闭/启动电源
- 请确认下载后的压缩文档文件未被损坏
- 请在未测试正常之前不要将 **zImage.old** 及旧版本的内核包删除


# 目标
此内核的对应Target为 **AML-S905d**。  
目前在N1上运行正常且平滑。

# 安装
请在终端执行以下命令:
```
dpkg -i *deb
mv /boot/zImage /boot/zImage.old
cp ./*dtb /boot/dtb/amlogic/
cp ./Image /boot/zImage
reboot
```
**(Linux 5.8 涉及的 DTB 覆盖: 安装脚本暂未更新，可按以上脚本进行安全安装。  
请确认 uEnv 中指定的DTB路径为 `/dtb/amlogic/meson-gxl-s905d-phicomm-n1.dtb` )**

# 声明
感谢[150balbes](https://github.com/150balbes)提供的repo以进行编译。  
**用户安装此内核而引发的问题均与 Starx 及原 REPO 作者无关。  
由于涉及到内核更换，错误的操作可能使你的系统无法启动。  
请务必小心谨慎执行。**

# 分享
本目录下的资源禁止分享至**恩山论坛**。  
本人极度厌恶其论坛的管理员，私自将本人的账号无理由封禁。  
其他论坛/群组/博客均可，但请务必保留 **Starx** 及 **原作者的REPO** 链接。
