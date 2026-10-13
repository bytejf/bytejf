# bytejf

**后端工程师 · LLM 应用与开发者工具**

我在做的一件事：把「确定性工程」和「LLM 推理」拼在一起。
能用规则判定的绝不交给模型，模型只负责它真正擅长的那部分 —— 语义判断。
这样出来的系统才**可复现、成本可控、缺口可审计**。

---

## 技术栈

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-v1-1C3C3C?style=flat-square)
![LangGraph](https://img.shields.io/badge/LangGraph-1.x-FF6F61?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-OTLP-425CC7?style=flat-square&logo=opentelemetry&logoColor=white)

### LLM 应用与 Agent
`LangChain v1` `LangGraph` `ReAct 循环` `Tool Use 与结构化输出` `Agent 控制流与中间件` `多组并发调度`

### 上下文工程
`Token 预算与装箱` `上下文压缩与结构化摘要` `Prefix Cache 复用` `长上下文与注意力退化控制`

### Agent 评测与实验设计
`LLM-as-Judge 判分口径` `P/R/F1 指标设计` `消融实验` `错例归因` `裁判抖动控制与置信区间` `变异测试`

### 代码分析与静态检查
`Tree-sitter / AST 符号提取` `Unified Diff 解析` `golangci-lint`

### Go 语言与底层机制
`GMP 调度模型` `并发原语` `内存与性能剖析` `GC 机制`

### 微服务架构与治理
`Kratos` `gRPC / Protobuf` `服务治理（限流 / 熔断 / 降级）` `注册中心与配置中心`

### 分布式中间件与存储
`Kafka（高吞吐调优 / 积压排查）` `Redis（分布式锁 / 缓存穿透与雪崩治理）` `MySQL（InnoDB / 索引调优 / 分库分表）`

### 云原生与可观测性
`OpenTelemetry / OTLP` `Prometheus / Grafana` `分布式链路追踪` `Docker / K8s`

---

## 在做的事

### [Prism](https://github.com/bytejf/prism) · 确定性优先的代码审查 Agent

传统 linter 只能抓模式化问题；纯 LLM 审查又贵、幻觉多、结果不可复现。
Prism 用混合架构解这个矛盾 —— **能用规则判定的绝不调 LLM**：
hunk 归属走 Tree-sitter AST，评论定位零 LLM（三层静态回退），
预算写成硬闸而不是提示词里的建议，超了带缺口退出并把缺口写进报告。

`Python` · `LangChain v1 / LangGraph` · `Tree-sitter` · `golangci-lint` · `OpenTelemetry`
