复习

shutdown

&&  前一个命令可以执行后执行  之后的命令

```bash
sleep 1
sleep 5 && date   //5秒后执行date

```

shutdown  本身并不准确    精确度是分钟

脚本的编写方式



系统服务的管理脚本，，在运维工作中会使用  ，，

可以写shell  任务shutdown

# 应用



版本控制   更改记录  

git  分布式            

github  托管应用使用的技术是git

应用  编写脚本  设置语言  搭载软件   配环境  一步实现   git上传 后下载运行

### 正则表达式

实训的时候文本处理   一定用到正则表达式  JAVA正则匹配的库

匹配文本   编辑软件配有相关库

搜索  是对字符串结构

```bash
linux.*\pdf$
```

.表示任意字符     * 表示前一个模式出现任意数目  \转义   $ 表示结尾



查找进程

```bash
ps -e | grep ssh
```

```bash
ls bin
vin bin/b

COMMAND='ps -e -
//照片1
```



这个匹配过程   ， p脚本 调用ps   ssh

```bash
p | grep 'ssh.*-D'
```

以管道交给grep匹配   

### 管道（复习）

”|“   这个就是管道   相当于两个进程     各自独立空间  但是 数据要给另外程序        

通常   输出一个文件  再读取

但是系统开一个空间 内存   数据传输的**管道**





   	正则表达式示例： ^(12|13|14|15|16|17|18|19)[0-9]{9}$ 

​	邮箱格式 匹配格式是否违法

### 元字符

 比如 . 表示任意字符，

 * 前一个模式出现任意次数，
 *  ^ 表示要从开头就要匹配。

元字符 

#### 说明

 ^ 匹配开头，			当 ^ 出现在正则表达式中间往往不作为元字符，但是这要看程序如何处理。

 . 					匹配任意字符。

​	 * 				前一个模式匹配任意次数。

 $ 尾匹配，			表示匹配结束正好是文本的末尾。

 	+ 				前一个模式出现 1 次或多次。

	\ 转义，				可以让元字符作为普通字符。

	{} 次数限制，		 {n}, {n,m}, {n,} 表示前一个模式出现 n 次， n 到 m 次， n 次及以 上。 

	] 范围集合，			 [0-9] 匹配 0 到 9 的字符， [0-9a-z] 匹配 0 到 9 或 a-z 的字符。js可以php也可以看环境 

	 逻辑或，（不是管道）	x|y 匹配 x 或 y 。



### grep

不支持 |   脚本会使用 egrep

● grep 是 Linux/Unix 上用于正则匹配的命令。

 ● grep 支持的正则引擎比较复杂，同时支持早期的和后来新 型的匹配引擎，属于混合类型。

 ● 默认使用 grep 支持的元字符有限，比如不支持 | 。

 ● 要使用功能更强的匹配则需要使用 egrep 或 grep -E 。 

 ```bash
egrep 'unix|linux'
标红表示匹配成功
会一直匹配
ctrl + d 退出  问什么是d呢  ？？？ 可以看asc码    

man ascii //看asc码
 ```

```bash
p | grep 'ssh.*-D'
```

egrep默认行匹配   /n表示换行  作为一个结尾    

如何多行匹配？？？  比如结构体信息  不要以换行作为结尾   

```bash
● 查找目录 /usr/include 中包含 struct stat 的结构
体，并搜索整个结构体的声明：
egrep -Rz ‘struct stat \{[^\}].*\}’ /usr/include
● 选项 z 表示多行匹配， [^\}] 则表示只要不包含 } 则匹配
成功。
```

打开文本时  会发现不换行的现象？？

\r	IOS默认

\r\n  windows默认

\n     Unix

### bash

```bash
ls -a

cat /etc/profile

etc目录是全局的
```



```bash
但是  每个用户可以有自己的配置  只针对用户有效
● bash 在首次会话登录的启动时，要去 /etc/ 中加载 /profile
配置文件。 (bash --login 方式启动 )

● 此外， bash 还会在当前用户主目录中按照顺序寻找

.bash_profile .bash_login .profile            改环境变量  在这  这个登录执行

● 之后读取 /etc/bash.bahsrc 以及用户主目录的：

.bash_bashrc .bashrc  						改在这，这个工作量大

● 并运行其中的命令。

```



```bash
l      相当于 ls -CF

ls
有区别
ls -F

cat .bashrc | less  //可以找ls

nano 

alias c='clear'     相当于起别名

输入c就相当于clear


生效

. .bahcrc   第一个. 相当于source

```



```bash
> 是输出重定向   
date > /tmp/logout_time

l /temp
cat /tmp/logout_time

这个是调整时区
sudo timedatectl st-time

sudo timedatectl st-timezone Aisa/Shanghai

```

