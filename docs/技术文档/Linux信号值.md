#LINUX信号 值

###POSIX.1列出信号值

>**SIGHUP** **1** A 终端挂起或者控制进程终止 
>**SIGINT** **2** A 键盘中断（如break键被按下） 
>**SIGQUIT** **3** C 键盘的退出键被按下 
>**SIGILL** **4** C 非法指令 
>**SIGABRT** **6** C 由abort(3)发出的退出指令 
>**SIGFPE** **8** C 浮点异常 
>**SIGKILL** **9** AEF Kill信号 
>**SIGSEGV** **11** C 无效的内存引用 
>**SIGPIPE** **13** A 管道破裂: 写一个没有读端口的管道 
>**SIGALRM** **14** A 由alarm(2)发出的信号 
>**SIGTERM** **15** A 终止信号 
>**SIGUSR1** **30**,10,16 A 用户自定义信号1 
>**SIGUSR2** **31**,12,17 A 用户自定义信号2 
>**SIGCHLD** **20**,17,18 B 子进程结束信号 
>**SIGCONT** **19**,18,25 进程继续（曾被停止的进程） 
>**SIGSTOP** **17**,19,23 DEF 终止进程 
>**SIGTSTP** **18**,20,24 D 控制终端（tty）上按下停止键 
>**SIGTTIN** **21**,21,26 D 后台进程企图从控制终端读 
>**SIGTTOU** **22**,22,27 D 后台进程企图从控制终端写 



###SUSv2列出信号值

> **SIGBUS** 10,7,10 C 总线错误(错误的内存访问) 
> **SIGPOLL** A Sys V定义的Pollable事件，与SIGIO同义 
> **SIGPROF** 27,27,29 A Profiling定时器到 
> **SIGSYS** 12,-,12 C 无效的系统调用 (SVID) 
> **SIGTRAP** 5 C 跟踪/断点捕获 
> **SIGURG** 16,23,21 B Socket出现紧急条件(4.2 BSD) 
> **SIGVTALRM** 26,26,28 A 实际时间报警时钟信号(4.2 BSD) 
> **SIGXCPU** 24,24,30 C 超出设定的CPU时间限制(4.2 BSD) 
> **SIGXFSZ** 25,25,31 C 超出设定的文件大小限制(4.2 BSD) 

- **PS**（对于SIGSYS，SIGXCPU，SIGXFSZ，以及某些机器体系结构下的SIGBUS，Linux缺省的动作是A (terminate)，SUSv2 是C (terminate and dump core)）。 

###其他信号值

> **SIGIOT** **6** **C** IO捕获指令，与SIGABRT同义 
> **SIGEMT** **7**,-,7 
> **SIGSTKFLT** -,**16**,- **A** 协处理器堆栈错误 
> **SIGIO** **23**,29,22 **A** 某I/O操作现在可以进行了(4.2 BSD) 
> **SIGCLD** -,-,**18** **A** 与SIGCHLD同义 
> **SIGPWR** **29**,30,19 **A** 电源故障(System V) 
> **SIGINFO** **29**,-,- **A** 与SIGPWR同义 
> **SIGLOST** -****,-,- **A** 文件锁丢失 
> **SIGWINCH** **28**,28,20 **B** 窗口大小改变(4.3 BSD, Sun) 
> **SIGUNUSED** -,31,- **A** 未使用的信号(will be SIGSYS) 

（在这里，- 表示信号没有实现；有三个值给出的含义为，第一个值通常在Alpha和Sparc上有效，中间的值对应i386和ppc以及sh，最后一个值对应mips。信号29在Alpha上为SIGINFO / SIGPWR ，在Sparc上为SIGLOST。） 

### 说明

- 处理动作一项中的字母含义如下 
  A 缺省的动作是终止进程 
  B 缺省的动作是忽略此信号 
  C 缺省的动作是终止进程并进行内核映像转储（dump core） 
  D 缺省的动作是停止进程 
  E 信号不能被捕获 
  F 信号不能被忽略 