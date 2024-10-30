# 文件和目录操作
## ls
ls 列举当前目录下的文件和目录

ls -l 或ll 列举所有文件的属性
-rwxr-x--- 1 root root       235 Jan 19  2024 add_anytime_config.sh  
第一个字母 d目录 -普通文件  
第二到第四个字母 owner权限 rwx 表示 read write 执行（在目录时表示进入）   
第五到第七个字母 group权限  
第八到第十个字母 others权限  
第一个数字 链接数  
第二个数字 文件大小  

ls -a 列出隐藏文件  
## cd
cd 进入目录  
cd ..  
cd ../.. 上上层目录  
cd . 本层目录  
**cd -** 回到上一次的目录  
## pwd
pwd 打印当前路径  
# 文本编辑相关
## cat/tail/head
### cat
cat 返回文件内容  
### head
head 看文件开头  
head --lines=2 README.md 看开头两行  
### tail
tail 看文件尾部  
## less/more
### less
less 看全文  
### more
more 看全文  
## nano/vim
### nano
nano 文本编辑器 下面有显示用法   
### vim
vim 文本编辑器  
i 进入编辑  
esc 退出编辑  
： 命令行模式  
q！强制退出  
wq 保存退出  
# 文件属性
## file
file 看文件属性  
## where/which
where 查看文件位置  
## find
find [路径] [匹配条件] [动作]  
find /path/to/search -name "clean*"  循环递归查找开头为clean的文件和目录  
find /path/to/search -type f -name "`*clean`*"  查找文件名中包含clean的文件
# 打印 echo
## echo
echo 打印文本  
h="hello" 定义变量  
echo $h 打印变量  
echo "abc$h" 打印变量  
echo "abc${h}efg" 这样写法更好  
# 其他技巧
## mv 重命名
mv test1 test2 重命名为test2  
## for 循环
for ff in *.sh 找到当前目录所有.sh文件  
循环体  
for>do  
for>echo ${ff}  
for>done  

tab键 自动补齐  
