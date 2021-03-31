ls /home/io:用户主目录/家目录
ls /lib

ls /media 可以看优盘里面的
ls /opt/很多软件会用到这个文件夹

ls /proc/
内存上并没有存储在硬盘上
ls /
ls /root默认情况下权限拒绝
sudo ls/root输权限密码
ls /var/log/
ls /sys/驱动、亮度、电源的目录（虚拟机无权限）

cd  chang direction
cp --help
man -s
man是查看外部命令的帮助手册
help是查看内部命令的帮助手册

type是查看命令是那种命令。
whereis ls
which查看路径



根据描述写出命令操作方式：

\1. 创建用户xyz。

sudo adduser xyz

\2. 创建用户组first。

sudo addgroup

\3. 让xyz用户加入first用户组。

sudo usermod -G first -a xyz

\4. 更改data目录以及所有子项都属于xyz用户，first用户组。

chown xyz:first tmp/ -R

\5. 针对目标文件 /etc/group 创建符号链接 $HOME/group。

ln -s /etc/group $HOME/group

## 第二次作业

·如何按照适合人类读取的方式显示文件信息和大小？（ls的使用）（1分）

ls -sh  

·在根目录创建/myshare目录，并设置sticky位允许其他用户可写？（2分）

mkdir myshare

chmod o=w,g=rx,o= myshare/ 



·简要介绍Linux，请说明Linux和Ubuntu、Debian、CentOS的关系？（3分）

Linux 是一个开源的操作系统内核 ， Linux 简洁、高效、功能强大。 Linux 在云计算、嵌入式领域占据统治地位。 

 Linux 本身是一个操作系统内核，制作发行一个操作系统 需要 Linux 内核、 GNU 项目软件、其他软件等。 

Linux和Ubuntu、Debian、CentOS的关系:是linux系统的发行版 。



·一个命令把文件/etc/default/grub 和 /etc/default/console-setup的内容保存到/tmp/etc-save？（不要更改原文件）（3分）

cat -b /etc/default/grub /etc/default/console-setup >> /tmp/etc-save



· 修改语言为中文：

> \1. 修改/etc/default/locale，把LANG=en_US.UTF-8改成LANG=zh_CN.UTF-8
>
> \2. 安装语言包：sudo apt install language-pack-zh-hans
>
> \3. 退出重新登录，运行env | grep LANGs
>
> \4. 安装中文手册：sudo  apt install manpages-zh
>
> \5. 如果man man不显示中文，则运行sudo locale-gen，然后退出重新登录。

**要求：**提交命令：man man的部分截图，有中文部分即可。（此时，man man显示的内容是中文文档。）（4分）

 sudo nano /etc/default/locale

LANG=zh_CN.UTF-8



·PID为1235的进程，捕获了常用的SIGINT、SIGTERM等信号，默认kill无法终止，如何强制退出？（2分）

kill -9 1235

·如何查看设备的内存大小和CPU信息？（提示：/proc）（3分）

cat /proc/meminfo 

cat /proc/cpuinfo 

·提交内存信息和CPU信息的命令运行结果截图。（2分）



//把参数遍历出来

```bash
for a in $@ ; do
	echo $a
done

#!/bin/bash
for a in $@ ; do
	echo $a
done
//这中需要交给bash运行
for((i=0;i<10;i++)) ; do
	echo $i
done
```

```bash
while date ; do
	sleep 1
	clear
done
```

```bash
while true : do
```

```bash
funca() {
    for a in $@ ; do
    	echo $a
    done
}
funca 1 2 3

for a in $@ ; do
	echo $@
donefun
```

chmod +x func_args.sh

./func_args.sh a b c

```bash
shutdown -h now  		立即关机，其中now相当于时间为0；
shutdown -h 13:02		在13:02时间关机，如果当期时间已经过了13:02，则是在明天的13:02关机；
shutdown -h +5			5分钟后关机；
shutdown -r now			立即重启；
```



```bash

if [ $# -eq 0 ]; then
    shutdown -h now
else
	sleep $@
	shutdown -h now
fi
```

