# FalmeGraph
火焰图查看
```
解压perf.tgz
执行perf命令，对进程进行perf
perf record -g -F 1000 -p [PID]
export PATH=`pwd`/FlameGraph:$PATH

perf script | stackcollapse-perf.pl | flamegraph.pl > perf.svg


在perf.svg目录下面执行 python -m SimpleHTTPServer 8015 开启http服务，在mac下载火焰图
```

ps:2系内核默认 /proc/sys/kernel/kptr_restrict = 1，会拒绝非root用户访问/proc/kallsyms获取内核符号表。  

这样跑perf top或者生成火山图，内核相关函数会缺失细节。  

解决：sudo perf xxx 或者  /proc/sys/kernel/kptr_restrict 设置为0 。
