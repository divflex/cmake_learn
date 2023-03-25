lldb学习

安装:
```
apt install lldb

# ModuleNotFoundError: No module named 'lldb.embedded_interpreter
apt install python3-lldb-14
ln -s /usr/lib/llvm-14/lib/python3.10/dist-packages/lldb/* /usr/lib/python3/dist-packages/lldb/
```

clang++ main.cpp -> a.out

如果是C语言：clang main.c

lldb a.out 
run (简写r)
> hello, world

这里编译时必须加-g参数，不然不能断点


---------------------------------

第5行设置断点：
breakpoint set -f main.c -l 5
简写
br s -f main.c -l #
b main.c:12

列出所有断点:
br list

删除
br del 1 # 1是br list开头的序号
br del 删除所有

通过函数名加断点
定义test函数
b test

--------------------------

next / n  下一行

step / s  下一步 / 会进入子函数

continue / c    继续执行（直到下一个断点）

--------------------------

打印当前变量
p name

当前栈帧变量
frame variable
fr v        查看当前栈帧的变量值

---------------------------
bt 调用栈

调用栈列出之后，可以用fr select切换当前栈帧
fr s 1 

----------------------------

监视断点（必须在执行时设置）
用于全局变量？

w list
w s v (wathpoint set variable [some globalVariable])

------------------------------
kill 程序停止，重新r运行


quit/exit 退出