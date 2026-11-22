---
name: perf-flamegraph-analyzer
description: 性能火焰图分析与系统瓶颈智能诊断专家技能 (由主机节点 B 随机生成用于跨端同步测试)。
version: 1.0.0
author: NodeB-Host
tags:
  - performance
  - profiling
  - flamegraph
  - node-b-test
---

# 性能火焰图分析器 (Perf Flamegraph Analyzer)

> 本技能由 **主机节点 B (Node B)** 独立创建，用于验证跨主机分布式同步与分发链路。

## 技能定位与核心能力
- **CPU 性能分析**：自动解析系统调用与热点函数消耗；
- **火焰图交互诊断**：支持快速定位宽平顶 (Plateau) 与深调用栈瓶颈；
- **多语言栈支持**：兼容 C/C++、Go、Rust、Java (async-profiler) 等多语言运行时调用链。

## 常用操作指引
1. 生成火焰图数据样本：
   ```bash
   perf record -F 99 -p <PID> -g -- sleep 10
   perf script | stackcollapse-perf.pl | flamegraph.pl > cpu-flamegraph.svg
   ```
2. 识别主线程及工作协程中的热点阻塞节点；
3. 输出优化重构建议与预期收益。
