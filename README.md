# install_nvidia_driver_on_ubuntu_18_10

## 禁用Nouveau开源驱动
在终端中
```bash
sudo vim /etc/modprobe.d/blacklist.conf
```
在文件中添加 blacklist nouveau
更新 initramfs
```bash
sudo update-initramfs -u
```
重启电脑

## 清理原nvidia驱动
```bash
sudo apt autoremove --purge nvidia*
```

## 下载Nvidia Driver
[https://www.nvidia.cn/Download/index.aspx](https://www.nvidia.cn/Download/index.aspx)

## 安装驱动
### 停止gdm
```bash
sudo service gdm stop
```
### 安装驱动

安装必要软件包
```bash
sudo apt install gcc make
```
ctrl+alt+f3进入虚拟控制台，登陆后
```bash
sudo ./NVIDIA-Linux-x86_64-XXX.XX.run
sudo apt install nvidia-prime nvidia-settings
reboot
```
## Extra
### 解决画面撕裂
```bash
sudo vim /etc/modprobe.d/nvidia-blacklists-nouveau.conf
```
添加`options nvidia_drm modeset=1`

```bash
sudo update-initramfs -u
```
