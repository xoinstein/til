## set -u / set -o nounset

改变bash默认忽略不存在的变量，而是报错且退出



## set -x / set -o xtrace

打印执行的命令



## set -e / set -o errexit

使脚本只要发生错误，就终止执行



## set -o pipefail

set -e 不适于管道命令，set -o pipefail 用来解决此情况，只要一个子命令失败，整个管道命令就会失败



参考链接

- 阮一峰的网络日志 [Bash 脚本 set 命令教程](http://www.ruanyifeng.com/blog/2017/11/bash-set.html)