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

##
