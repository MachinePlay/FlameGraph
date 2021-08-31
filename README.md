# FalmeGraph
火焰图查看
```
export PATH=`pwd`/FlameGraph:$PATH

perf script | stackcollapse-perf.pl | flamegraph.pl > perf.svg


在perf.svg目录下面执行 python -m SimpleHTTPServer 8015 开启http服务，在mac下载火焰图
```
