ctrl-c 发送 SIGINT 信号给前台进程组中的所有进程。常用于终止正在运行的程序。
ctrl-z 发送 SIGTSTP 信号给前台进程组中的所有进程，常用于挂起一个进程。
ctrl-d 不是发送信号，而是表示一个特殊的二进制值，表示 EOF。
ctrl-\ 发送 SIGQUIT 信号给前台进程组中的所有进程，终止前台进程并生成 core 文件。

Key Function
Ctrl-c Kill foreground process
Ctrl-z Suspend foreground process
Ctrl-d Terminate input, or exit shell
Ctrl-s Suspend output
Ctrl-q Resume output
Ctrl-o Discard output
Ctrl-l Clear screen


　总结:
　　(1) CTRL+Z挂起进程并放入后台
　　(2) jobs 显示当前暂停的进程
　　(3) bg %N 使第N个任务在后台运行(%前有空格)
　　(4) fg %N 使第N个任务在前台运行
　　默认bg,fg不带%N时表示对最后一个进程操作!
  
  TODO:
  ctrl + c是挂起一个进程还是多个进程？？？
  ctrl + z同上待测试
