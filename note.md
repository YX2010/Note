# Wifi

```
0: phy0: Wireless LAN
	Soft blocked: no
	Hard blocked: yes
1: asus-wlan: Wireless LAN
	Soft blocked: no
	Hard blocked: no
```

## solve
[参考教程](https://www.bbsmax.com/A/Gkz109ZZdR)
1. `lspci -nnk | grep -A2 0280`

```
03:00.0 Network controller [0280]: Qualcomm Atheros AR9485 Wireless Network Adapter [168c:0032] (rev 01)
	Subsystem: Lite-On Communications Inc AR9485 Wireless Network Adapter [11ad:6627]
	Kernel driver in use: *ath9k*
```

2. `lsmod | grep -e ath9k -e asus`
3. `rfkill list all`
4. 将系统挂起，然后重启, wifi正常使用


5. 创建创建，添加内容
```
/etc/modprobe.d/asus_nb_wmi.conf
options asus_nb_wmi wapf=4
```

# Install rime
/home/yangxu/.config/ibus/rime/default.yaml

# Linux 忘记用户用与密码
1. 重启系统
2. 长按`shift`直到出现菜单。选择`recovery mode`
3. 选择`root`
4. `/etc/passwd` 查看用户名
5. `passwd username`
6. 重启 `reboot`
