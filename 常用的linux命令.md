## 一.终端命令格式
```linux
command [-option] [parameter]
```
command：命令名称 

[option]：选项，用来对命令进行控制，也可以省略

[parameter]：传给命令的参数，可以是0个、一个或多个

[]代表可选

## 二.常见命令
|  序号  |  命令  |  对应英文  |  作用  |  备注 |
|  ----  | ---- |  ----  |  ----  |  ----  |
|01|ls|list|查看当前文件下的内容||
|02|pwd|print work directory|查看当前所在文件路径||
|03|cd[目录名]|change directory|切换文件夹||
|04|touch|touch[]文件名|如果文件不存在则新建文件||
|05|mkdir[目录名]|make directory|创建目录||
|06|rm[文件名]|remove|删除文件||
|07|clear|clear|清屏||

## 三.查阅命令帮助信息
- --help
```linux
command --help
```
- man(manual的缩写)
```linux
man command
```
使用man时的操作键
|操作键|功能|
|  ----  |  ----  |
|空格键|显示手册页下一屏|
|enter|一次滚动一行|
|b|回滚前一屏|
|f|前滚一屏|
|/word|搜索word字符串|
## 四.查看目录内容
### 终端实用技巧
- 自动补全
    - 在敲出文件/目录/命令的前几个字母之后，按tab键
    - 如果还存在其他文件/目录/命令，再按一次tab键，系统会提示可能存在的命令
- 曾经使用过的命令
    - 按上下键可以在曾经使用过的命令之间切换
### ls命令说明
- 其功能为列出目录的内容，类似于DOS下的dir命令
- 以 . 开头的文件为隐藏文件，需要-a参数才能显示
- .代表当前目录
- ..代表上一级目录
```
zx@ubuntu:~$ cd Desktop/
zx@ubuntu:~/Desktop$ cd ..
zx@ubuntu:~$ cd .
zx@ubuntu:~$ 

```
- ls常用选项

|参数|含义|
|  ----  |  ----  |
|-a|显示指定目录下所有子目录和文件，包括隐藏文件|
|-l|以列表的方式显示文件的详细信息|
|-h|配合-l以人性化的方式显示文件大小|
|-lha|以上三个的结合|
```linux
zx@ubuntu:~$ pwd
/home/zx
zx@ubuntu:~$ ls
Desktop    Downloads         Music     Public     Videos
Documents  examples.desktop  Pictures  Templates
zx@ubuntu:~$ ls -a
.              Desktop           .ICEauthority  .sudo_as_admin_successful
..             .dmrc             .local         Templates
.bash_history  Documents         .mozilla       Videos
.bash_logout   Downloads         Music          .Xauthority
.bashrc        examples.desktop  Pictures       .xinputrc
.cache         .gconf            .profile       .xsession-errors
.config        .gnupg            Public         .xsession-errors.old
zx@ubuntu:~$ ls -l
total 44
drwxr-xr-x 2 zx zx 4096 Apr  1 14:29 Desktop
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Documents
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Downloads
-rw-r--r-- 1 zx zx 8980 Feb 18 06:31 examples.desktop
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Music
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Pictures
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Public
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Templates
drwxr-xr-x 2 zx zx 4096 Feb 18 06:32 Videos
zx@ubuntu:~$ ls -h
Desktop    Downloads         Music     Public     Videos
Documents  examples.desktop  Pictures  Templates
zx@ubuntu:~$ ls -l -h
total 44K
drwxr-xr-x 2 zx zx 4.0K Apr  1 14:29 Desktop
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Documents
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Downloads
-rw-r--r-- 1 zx zx 8.8K Feb 18 06:31 examples.desktop
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Music
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Pictures
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Public
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Templates
drwxr-xr-x 2 zx zx 4.0K Feb 18 06:32 Videos
zx@ubuntu:~$ ls -lha
total 116K
drwxr-xr-x 16 zx   zx   4.0K Apr  1 04:13 .
drwxr-xr-x  3 root root 4.0K Feb 18 06:31 ..
-rw-------  1 zx   zx    840 Apr  1 14:37 .bash_history
-rw-r--r--  1 zx   zx    220 Feb 18 06:31 .bash_logout
-rw-r--r--  1 zx   zx   3.7K Feb 18 06:31 .bashrc
drwx------ 14 zx   zx   4.0K Apr  1 04:34 .cache
drwx------ 16 zx   zx   4.0K Apr  1 04:34 .config
drwxr-xr-x  2 zx   zx   4.0K Apr  1 14:29 Desktop
-rw-r--r--  1 zx   zx     25 Feb 18 06:32 .dmrc
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Documents
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Downloads
-rw-r--r--  1 zx   zx   8.8K Feb 18 06:31 examples.desktop
drwx------  2 zx   zx   4.0K Feb 18 06:33 .gconf
drwx------  3 zx   zx   4.0K Apr  1 04:13 .gnupg
-rw-------  1 zx   zx   1.6K Apr  1 04:13 .ICEauthority
drwx------  3 zx   zx   4.0K Feb 18 06:32 .local
drwx------  5 zx   zx   4.0K Feb 18 06:40 .mozilla
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Music
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Pictures
-rw-r--r--  1 zx   zx    655 Feb 18 06:31 .profile
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Public
-rw-r--r--  1 zx   zx      0 Feb 18 07:19 .sudo_as_admin_successful
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Templates
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Videos
-rw-------  1 zx   zx     51 Apr  1 04:13 .Xauthority
-rw-rw-r--  1 zx   zx    131 Feb 18 06:41 .xinputrc
-rw-------  1 zx   zx     82 Apr  1 04:13 .xsession-errors
-rw-------  1 zx   zx   1.5K Apr  1 04:11 .xsession-errors.old

```
- ls通配符的使用

|通配符|含义|
|  ----  |  ----  |
|*|代表任意个数个字符|
|？|代表任意一个字符|
|[]|表示可以匹配字符组中任意一个|
|[abc]|匹配abc中的任意一个|
|[a-f]|匹配从a-f范围内的任意一个字符|
## 五.切换目录
### cd
linux所有的目录和文件名全是大小写敏感的
|命令|含义|
|  ----  |  ----  |
|cd|切换到当前用户的主目录（/home/用户目录）|
|cd ~|切换到当前用户的主目录（/home/用户目录)|
|cd .|保持当前目录不变|
|cd ..|切换到上级目录|
|cd -|在最近两次工作目录之间来回切换|

### 相对路径和绝对路径
```linux
zx@ubuntu:~$ pwd
/home/zx
zx@ubuntu:~$ cd /home/zx/Desktop/
zx@ubuntu:~/Desktop$ pwd
/home/zx/Desktop

```

## 六.创建和删除操作
### touch
- 如果文件不存在，可以创建一颗空白文件
- 如果文件存在，则修改文件的最末一次修改时间

### mkdir
创建一个新的目录

|命令|含义|
|  ----  |  ----  |
|-p|可以递归创建目录|
```
zx@ubuntu:~/Desktop$ mkdir -p a/b/c

```
### rm
删除文件或目录

|命令|含义|
|  ----  |  ----  |
|-f|强制删除，忽略不存在的文件，无需提示|
|-r| 递归的删除目录下的内容，删除文件夹必须加此参数|

```
zx@ubuntu:~/Desktop$ mkdir -p a/b/c/d
zx@ubuntu:~/Desktop$ cd a
zx@ubuntu:~/Desktop/a$ cd b
zx@ubuntu:~/Desktop/a/b$ cd c
zx@ubuntu:~/Desktop/a/b/c$ cd d
zx@ubuntu:~/Desktop/a/b/c/d$ cd ~
zx@ubuntu:~$ cd Desktop/
zx@ubuntu:~/Desktop$ rm -r a
zx@ubuntu:~/Desktop$ 

```

## 七.拷贝和移动文件

|命令|对应英文|作用|
|  ----  |  ----  |  ----  |
|tree[目录名]|tree|以树状图列出文件目录结构
|tree -d    | |只显示目录|
|cp 源文件 目标文件 |copy| 复制文件或目录
|cp -f||已经存在的目标文件直接覆盖，不会提示|
|cp -i||覆盖文件前提示
|cp -r||若给出的源文件是目录文件，则cp，将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名|
|mv|move|移动文件或者目录，也可以给文件或目录重命名
|mv -i||覆盖文件前提示

## 八.查看文件内容
|命令|对应英文|作用|
|  ----  |  ----  |  ----  |
|cat 文件名|concatenate|查看文件内容、创建文件、文件合并、追加文件内容等功能
|more 文件名|more|分屏显示文件内容
|grep 文件名|grep|搜索文本文件内容

### cat
- cat查看文件内容、创建文件、文件合并、追加文件内容等功能
- cat会一次显示所有的内容，适合查看内容较少的文本文件

|命令|作用|
|  ----  |  ----  |
|-b|对非空输出行编号|
|-n|对输出的所有行编号|

- linux中还有一个nl命令和cat -b 等价

### more
- 用来分屏显示文件内容，每次只显示一页内容

|操作键|功能|
|  ----  |  ----  |
|空格键|显示手册页下一屏|
|enter|一次滚动一行|
|b|回滚前一屏|
|f|前滚一屏|
|/word|搜索word字符串| 


### grep
- grep是一种强大的文本搜索工具
- 允许对文本文件进行正则表达式查找

|操作键|功能|
|  ----  |  ----  |
|-n|显示匹配行及行号|
|-v|显示不包含匹配文本的所有行（相当求反）|
|-i|忽略大小写|

```
zx@ubuntu:~$ cd Desktop/
zx@ubuntu:~/Desktop$ cat 123.txt
test
zx 
lbwnb
zhaoxuan
dididididi
zx@ubuntu:~/Desktop$ cat -b 123.txt
     1	test
     2	zx 
     3	lbwnb
     4	zhaoxuan
     5	dididididi
zx@ubuntu:~/Desktop$ grep x 123.txt
zx 
zhaoxuan
zx@ubuntu:~/Desktop$ grep -n zx 123.txt
2:zx 
zx@ubuntu:~/Desktop$ grep -v zx 123.txt
test
lbwnb
zhaoxuan
dididididi
zx@ubuntu:~/Desktop$ 


zx@ubuntu:~/Desktop$ cat 123.txt
test
zx 
lbwnb
zhaoxuan
dididididi
hello zx
zx@ubuntu:~/Desktop$ grep -n hello zx 123.txt
grep: zx: No such file or directory
123.txt:6:hello zx
zx@ubuntu:~/Desktop$ grep -n "hello zx" 123.txt 
6:hello zx
zx@ubuntu:~/Desktop$ 

```

## 其他
### 1. echo 文字内容

- 会在终端显示参数指定的文字，通常和 __重定向__ 联合使用 

### 2. 重定向> 和>>

- linux允许将命令执行结果重定向到一个文件
- 将本来应该显示在终端上的内容输出/追加到指定文件中
- __\>表示输出，会覆盖文件原有的内容__
- __\>>表示追加，添加内容到文件末尾__
    
```
zx@ubuntu:~/Desktop$ cat 123.txt
test
zx 
lbwnb
zhaoxuan
dididididi
hello zx
zx@ubuntu:~/Desktop$ echo hello gouxaun
hello gouxaun
zx@ubuntu:~/Desktop$ echo hello gouxaun > 123.txt
zx@ubuntu:~/Desktop$ cat 123.txt
hello gouxaun
zx@ubuntu:~/Desktop$ echo hello gouqiu >> 123.txt
zx@ubuntu:~/Desktop$ cat 123.txt
hello gouxaun
hello gouqiu

```
```
zx@ubuntu:~/Desktop$ ls -lh
total 4.0K
-rw-rw-r-- 1 zx zx 27 Apr  2 04:32 123.txt
zx@ubuntu:~/Desktop$ ls -lh >> 123.txt
zx@ubuntu:~/Desktop$ cat 123.txt
hello gouxaun
hello gouqiu
total 4.0K
-rw-rw-r-- 1 zx zx 27 Apr  2 04:32 123.txt

```
### 3.管道 |
- linux允许将 __一个命令的输出__ 可以 __通过管道__ 作为 __另一个命令的输入__
- 常用的管道命令有：
    - more：分屏显示内容
    - grep：在命令执行结果的基础上查询指定的文本

```
zx@ubuntu:~/Desktop$ ls -lha ~ | grep Do
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Documents
drwxr-xr-x  2 zx   zx   4.0K Feb 18 06:32 Downloads

```