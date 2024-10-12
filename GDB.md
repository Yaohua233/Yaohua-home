➢ 示例代码编译
  • 编译：gcc -g3 demo.c -lpthread -o demo
  • 说明：-g3用于编译产生调试信息；
          -lpthread用于链接动态库；
          -o用于指示生成目标文件名；
➢ 启动GDB调试
  • gdb <program> 启动进入调试
  • gdb <program> <core> 调试程序core文件
  • gdb <program> <pid> 调试指定PID的运行中程序
➢ 指定参数运行目标程序
  • start <args> 启动调试程序并停在主程序入口处
  • run <args> 启动调试程序直接进入运行，可简写为：r <args>
➢ 中断调试
  • [Ctrl + C] GDB拉起程序后，按下Ctrl键和字母C键，可中断正在运行的程序回到GDB命令端
➢ GDB与shell切换
  • shell 从(GDB)命令端切换到shell终端，从shell切回可以使用exit
  • shell <command> 在GDB中执行指定的shell命令
➢ 退出调试
  • quit 结束退出GDB调测，简写：q
➢ 查看源码
  • list ，简写：l
  • list <linenum> 查看指定行号的代码
  • list <begin> <end> 查看行号从begin到end的代码
  • list <+/- offset> 查看当前行号正负偏移量
  • list <file:linenum> 查看指定文件：指定行号的代码
  • list <func> 查看函数代码
  • list <file:func> 查看指定文件：指定函数的代码
  • list *<address> 查看程序运行时在指令地址的源码语句
  • show list 查看当前显示源代码的行数
  • set list <num> 设置一次显示源码的行数
➢ 查看汇编
  • disassemble，简写：disas
  • disas <func> 查看函数反汇
  • disas 0x<hhhhhh> 查看指定地址的函数反汇编（前提这里是函数的指令地址）


➢ 设置断点
  • break，简写：b 断点停住程序后，可以使用continue恢复运行
  • b <linenum> 指定源码行号打断点
  • b <func> 指定源码函数入口打断点
  • b <file:line> 指定源码文件及行号打断点
  • b <file:func> 指定源码文件及函数名打断点，适用于静态函数
  • b *<address> 指定地址打断点（适用于结合汇编使用）
➢ 查看断点
  • info，简写：i
  • info break 查看断点信息，可简写为：i b
  • info break n 根据断点号查看指定断点信息
➢ 管理断点
  • delete <n> 删除断点，n为info break中看到断点的编码，可简写为：d
  • disable <n> 禁用断点，使之不生效，程序运行至此不会停住
  • enable <n> 恢复被禁用的断点，程序运行至此将会被停住
  • clear <expr> 清除断点，如同设置断点一样，需要指定断点位置

➢ 数据断点命令
  • watch 当表达式或变量值被写时，停止程序
  • rwatch 当表达式或变量值被读时，停止程序
  • awatch 当表达式或变量值被读写时，停止程序
➢ 设置数据断点
  • watch <expr> 监视变量
  • watch *<address> 监视指定地址的内存，有效防止非法修改
  注：watch、rwatch、awatch的使用方式和参数格式都是一致的
➢ 查看数据断点
  • info watchpoint 查看当前程序中设置的数据断点信息

➢ 断点打印
  • display <expr> 每次断点都会自动打印expr信息
  • undisplay 取消前面使能的display
➢ 条件断点
  • condition <bnum> <expr> 设置条件断点，满足条件时停住
  • b <location> if <expr> 打断点时指定条件
  •  ignore <bnum> <count> 忽略断点执行的次数
➢ 断点命令
• commands <bnum>
[…command-1…]
[…command-2…]
[…command-3…]
…
end
