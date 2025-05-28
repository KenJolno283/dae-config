#  我的dae配置样本
dae是一款高性能的透明代理工具，并且利用Linux内核中的eBPF技术实现了绕过代理程序直接转发的直接分流。

## 系统要求
- 内核版本**5.17**以上
- 并且需要以下内核选项

```
CONFIG_BPF=y
CONFIG_BPF_SYSCALL=y
CONFIG_BPF_JIT=y
CONFIG_CGROUPS=y
CONFIG_KPROBES=y
CONFIG_NET_INGRESS=y
CONFIG_NET_EGRESS=y
CONFIG_NET_SCH_INGRESS=m
CONFIG_NET_CLS_BPF=m
CONFIG_NET_CLS_ACT=y
CONFIG_BPF_STREAM_PARSER=y
CONFIG_DEBUG_INFO=y
# CONFIG_DEBUG_INFO_REDUCED is not set
CONFIG_DEBUG_INFO_BTF=y
CONFIG_KPROBE_EVENTS=y
CONFIG_BPF_EVENTS=y
```

详细内容请参考官方仓库的[中文文档]（https://github.com/daeuniverse/dae/tree/main/docs/zh）

---
在routing中我另外增加了几行针对steam服务器的规则，其中``domain(geosite:category-games@cn``一行并没有亲测产生什么效果，只是为了以防万一加上的。同时，如果不在意或者不希望steam流量走直连的朋友可以直接把那几行注释掉。
