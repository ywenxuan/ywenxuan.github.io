# bash命令

### **--help 显示帮助文档**

如：date --help

![](.\截图\date命令help.png)

### passwd设置密码

### su进入超级用户模式

### file查看文件的类型

### 查看文件内容：

#### cat

快速：直接跳到文档结尾

![](.\截图\cat命令help.png)

|         | **cat 选项**                                                 |
| ------- | ------------------------------------------------------------ |
| -n      | 对所有行编号，从1开始                                        |
| -b      | 只对非空行编号，覆盖"-n"选项                                 |
| -A      | 等价于"-vET"组合选项。                                       |
| -E / -e | 行尾追加$                                                    |
| -s      | 压缩连续的空行到一行                                         |
| -T      | 使用"^I"表示TAB（制表符）                                    |
| -t      | 等价于"-vT"组合选项                                          |
| -v      | 使用"^"和"M-"符号显示控制字符，除了LFD（line feed，即换行符'\n'）和TAB（制表符） |
|         |                                                              |

|                  |                 |
| ---------------- | --------------- |
| cat 显示多文件： | cat f1 f2       |
| cat合并文件      | cat f1 f2 >> f3 |
|                  |                 |

#### less

慢速：打开文件首，方向键上下行，空格翻页

#### more

慢速：打开文件首

#### head 默认10行

```shell
-c, --bytes=[-]NUM       显示前NUM字节；如果NUM前有"-"，那么会打印除了文件末尾的NUM字节以外的其他内容。
-n, --lines=[-]NUM       显示前NUM行而不是默认的10行；如果NUM前有"-"，那么会打印除了文件末尾的NUM行以外的其他行。
-q, --quiet, --silent    不打印文件名行。
-v, --verbose            总是打印文件名行。
-z, --zero-terminated    行终止符为NUL而不是换行符。
```

#### tail 默认10行

```shell
-c, --bytes=NUM                 输出文件尾部的NUM（NUM为整数）个字节内容。
-f, --follow[={name|descript}]  显示文件最新追加的内容。“name”表示以文件名的方式监视文件的变化。
-F                              与 “--follow=name --retry” 功能相同。
-n, --line=NUM                  输出文件的尾部NUM（NUM位数字）行内容。
--pid=<进程号>                  与“-f”选项连用，当指定的进程号的进程终止后，自动退出tail命令。
-q, --quiet, --silent           当有多个文件参数时，不输出各个文件名。
--retry                         即是在tail命令启动时，文件不可访问或者文件稍后变得不可访问，都始终尝试打开文件。使用此选项时需要与选项“--follow=name”连用。
-s, --sleep-interal=<秒数>      与“-f”选项连用，指定监视文件变化时间隔的秒数。
-v, --verbose                   当有多个文件参数时，总是输出各个文件名。
```

#### wc统计文件信息

```shell
wc test.txt
# 输出结果
7     8     70     test.txt
# 行数 单词数 字节数 文件名

-c # 统计字节数，或--bytes或——chars：只显示Bytes数；。
-l # 统计行数，或——lines：只显示列数；。
-m # 统计字符数。这个标志不能与 -c 标志一起使用。
-w # 统计字数，或——words：只显示字数。一个字被定义为由空白、跳格或换行字符分隔的字符串。
-L # 打印最长行的长度。
```

### 多个命令之间用分号间隔如 ls;pwd

### bash补全、命令行换行、History

Tab 补全 命令、选项、参数

命令行换行：空格反斜杠 + 换行

**history 列出历史命令**

```shell
-c           清空历史列表。
-a           将当前终端的历史记录行添加到历史记录文件。
-w           将当前历史记录列表附加到历史记录文件中并且附加它们到历史列表中。

-d offset    根据offset删除记录。如果是正数则表示offset位置的记录，如果为负数则表示从结尾向前offset位置的记录。
-n           将尚未从历史文件中读取的历史行追加到当前历史列表中。
-r           读取历史文件，并将其内容附加到历史列表中。
-p           在每个arg上执行历史记录扩展并在标准输出上显示结果，而不将结果存储在历史记录列表中。
-s           将每个arg作为单个条目附加到历史记录列表。
!            调用历史命令，加数字匹配具体命令，如：!5；加字符串从下向上找最近（新）的命令进行匹配，如!cat

关闭终端后，历史列表将被写入历史文件~/.bash_history 
```

