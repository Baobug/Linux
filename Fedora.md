### Fedora安装上手配置


 **1. 终端快捷键设置** 


点击设置

键盘

将 中文（智能拼音） 设置为第一输入源

点击键盘快捷键

自定义快捷键——> +号

在name框中填写这个快捷键的名称，比如open terminal(打开终端窗口)

在command框中填写执行这个快捷键的shell命令，此处可填写gnome-terminal

设置快捷键组合

点击添加


 **2.安装edge** 

更新系统现所有软件包

```
sudo dnf upgrade --refresh
```

导入微软存储库

```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```

添加存储库 Microsoft RPM 存储库

```
sudo dnf config-manager --add-repo https://packages.microsoft.com/yumrepos/edge
```

安装edge稳定版

```
sudo dnf install microsoft-edge-stable
```


 **3.添加Flathub存储库** 


```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

**4.安装GNOME优化和扩展**


```
sudo dnf install gnome-tweaks gnome-extensions-app
```

**安装美化主题**

安装主题：

```
sudo dnf install flat-remix-theme

```
安装图标：

```
sudo dnf install numix-icon-theme-circle
```

安装光标：

```
sudo dnf install breeze-cursor-theme
```

**5.用于电池健康管理的TLP**

安装：

```
sudo dnf install tlp tlp-rdw
```

设置开机启动：

```
sudo systemctl enable tlp.service
```

屏蔽蓝牙、Wifi等：

```
sudo systemctl mask systemd-rfkill.service systemd-rfkill.socket
```
