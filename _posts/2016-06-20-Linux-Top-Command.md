---
layout:     post
title:      "Linux命令学习-top命令"
subtitle:   " \"了解top的用法\""
date:       2016-06-20 13:18:00
author:     "Dunno"
header-img: "img/post-bg-2015.jpg"
tags:
    - Linux
---

# 目录

- <a href="#bj">背景</a>
- <a href="#ckzl">参考资料</a>
- <a href="#xkd">先看懂top的输出吧</a>
- <a href="#tcy">top常用的一些命令</a>
- <a href="#jtd">具体的示例</a>


# <a name="bj">背景</a>
<p>top命令是Linux下常用的性能分析工具,特别是应用性能报警的时候，我们经常会用到这个命令</p>

# <a name="ckzl">参考资料</a>
> https://linuxaria.com/howto/understanding-the-top-command-on-linux

> http://linuxtools-rst.readthedocs.io/zh_CN/latest/tool/top.html?highlight=top

# <a name="xkd">先看懂top的输出吧</a>
<p>我们先运行一下top命令</p>
<pre>
<code>
top - 13:26:40 up 188 days, 20:28,  1 user,  load average: 0.07, 0.05, 0.05
Tasks: 145 total,   1 running, 144 sleeping,   0 stopped,   0 zombie
Cpu(s):  0.7%us,  0.3%sy,  0.0%ni, 99.0%id,  0.0%wa,  0.0%hi,  0.0%si,  0.0%st
Mem:   8059416k total,  7374232k used,   685184k free,   288420k buffers
Swap:  2096440k total,        0k used,  2096440k free,  5570192k cached

  PID USER      PR  NI  VIRT  RES  SHR S %CPU %MEM    TIME+  COMMAND     
 8182 sankuai   20   0  981m  40m 3420 S  3.0  0.5 180:24.71 sg_agent 
17939 sankuai   20   0 3612m 996m  17m S  1.7 12.7 639:16.22 java 
 8193 sankuai   20   0 1045m  29m 3152 S  1.3  0.4  84:28.97 sg_agent_worker   
10107 sankuai   20   0  268m 6724 3616 S  0.3  0.1   7:05.65 log_agent_file    
    1 root      20   0 23500 1552 1212 S  0.0  0.0   0:05.93 init 
    2 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kthreadd 
    3 root      RT   0     0    0    0 S  0.0  0.0   0:54.01 migration/0       
    4 root      20   0     0    0    0 S  0.0  0.0   3:28.67 ksoftirqd/0       
    5 root      RT   0     0    0    0 S  0.0  0.0   0:00.00 migration/0
</code>
</pre>


- 第一行内容-top
	- 13:26:40 **系统当前时间**
	- 188 days, 20:28, **系统开机到现在经过了多少时间**
	- 1 user, **当前1个用户在线**
	- load average: 0.07, 0.05, 0.05 **系统1分钟、5分钟、15分钟的CPU负载信息**
- 第二行内容-task
	- Tasks **任务,右边的数字也就是一个对任务的统计信息**
	- 145 total, **任务总数**	
	- 1 running, **运行的任务总数**
	- 144 sleeping, **休眠的任务总数**
	- 0 stopped, **停止的任务总数**
	- 0 zombie, **等待父进程来停止的任务总数**
- 第三行内容-cpu
	- 0.7%us (_user processes_)用户进程的CPU百分比,不包含renice值为负的任务。
	- 0.3%sy (_system processes_)系统进程的CPU百分比。
	- 0.0%ni (processes with priority _upgrade nice_)改变过优先级的进程的CPU百分比。
	- 99.0%id 没被利用的CPU百分比。
	- 0.0%wa (processes _waiting_ for I/O operations)等待I/O的CPU百分比。
	- 0.0%hi (_hardware interrupts_)硬中断的CPU百分比。
	- 0.0%si (_software interrupts_)软终端的CPU百分比。
	- 0.0%st (_Steal Time_)通常我们服务器是一个虚拟机，这个指标就代表目前我们所在的虚拟机偷取的整个物理机的CPU的总和。
- 第四行和第五行内容-内存利用	

# <a name="tcy">top常用的一些命令</a>

# <a name="jtd">具体的示例</a>








 