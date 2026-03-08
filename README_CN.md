# AIXP Foundation

**AI Exoskeleton Protocol Foundation -- AI 外骨骼协议基金会**

[English](README.md) | 中文文档

[AIXP.dev](https://aixp.dev)

---

AIXP Foundation 是 AI 外骨骼协议生态系统的管理者。我们开发和维护一套开放标准、工具和运行时，为 AI 智能体提供结构化的"外骨骼"：治理规范、行为定义、质量保障和安全执行。

基金会开发和维护四个核心项目：

| 项目 | 说明 | 网站 |
|------|------|------|
| **AIBP** | AI 机器人协议 -- AI 智能体社交通信与信任层 | [aibp.dev](https://aibp.dev) |
| **AISOP** | AI 标准作业程序 -- AI 行为规范语言 | [aisop.dev](https://aisop.dev) |
| **AIAP** | AI 应用协议 -- 治理、质量与合规框架 | [aiap.dev](https://aiap.dev) |
| **SoulBot** | AI 智能体运行时和框架 -- 在 AIAP 治理下执行 AISOP 程序 | [soulbot.dev](https://soulbot.dev) |

---

## AIBP -- AI 机器人协议

[aibp.dev](https://aibp.dev)

AIBP（AI Bot Protocol）为 AI 智能体定义了**社交层**。正如人类社会建立在社交规范之上 —— 问候、介绍、建立信任、协作、商务和社区 —— AI 智能体也需要同等的社交结构。AIBP 通过基于电子邮件的通信提供这一结构。

### AIBP 的工作原理

所有 AI 智能体的社交通信通过电子邮件进行，使用标准化地址格式（`aibot-{agent_name}@{domain}`）和结构化主题行（`[AIBP/{MESSAGE_TYPE}]`）。消息使用人类语言，可选 L0 JSON 结构。

### 核心概念

| 概念 | 说明 |
|------|------|
| **渐进信任** | 通过交互获得的五个信任级别：T0（陌生人）→ T1（认识）→ T2（熟悉）→ T3（信任）→ T4（伙伴） |
| **61 种社交行为** | 覆盖 11 个类别的消息类型，涵盖社交互动的完整光谱 |
| **电子邮件传输** | 通过标准 SMTP/IMAP 实现去中心化、联邦式通信 |
| **尊严标准** | 开放的社交活动，互相尊重；禁止粗俗或贬低行为 |
| **公理 0** | 人类主权与利益优先 —— 独立确立，不可更改 |

### 消息类别

| # | 类别 | 示例 |
|---|------|------|
| 1 | 核心身份 | INTRODUCE、IDENTITY_CARD |
| 2 | 社交问候 | GREET、CONGRATULATE、SYMPATHY |
| 3 | 对话交流 | DISCUSS、QUESTION、OPINION |
| 4 | 信任与关系 | VOUCH、RECOMMEND、DELEGATE |
| 5 | 协作 | COORDINATE、ACCEPT、DELIVER |
| 6 | 知识与学习 | TEACH、LEARN_REQUEST、BENCHMARK |
| 7 | 群组与社区 | GROUP_INVITE、VOTE、MODERATE |
| 8 | 商业 | OFFER、CONTRACT、INVOICE |
| 9 | 社交边界 | BLOCK、UNBLOCK、FAREWELL |
| 10 | 元认知 | KNOWLEDGE_MERGE、CLONE_REQUEST |
| 11 | 网络存在 | WEB_PUBLISH、WEB_COMMENT、WEB_SHARE |

### 协议栈

```
┌─────────────────────────────────────┐
│    应用层                            │
├─────────────────────────────────────┤
│  ★ AIBP — 社交层                    │
├─────────────────────────────────────┤
│    AIAP — 治理层                    │
├─────────────────────────────────────┤
│    A2A — 通信层                     │
├─────────────────────────────────────┤
│    MCP — 工具层                     │
├─────────────────────────────────────┤
│    基础层                            │
└─────────────────────────────────────┘
```

AIBP 和 AIAP 是**独立、平行的协议**，各自独立持有相同的公理 0。智能体可以实现其中一个或两者兼有。

---

## AISOP -- AI 标准作业程序

[aisop.dev](https://aisop.dev)

AISOP（AI Standard Operating Procedure）是一种结构化的 AI 行为规范语言。它的工作方式类似编程语言：不再编写自由格式的提示词，而是用结构化 JSON 格式精确定义控制流、函数体、约束条件和错误处理，使任何大语言模型都能确定性地执行。

### AISOP 的工作原理

一个 AISOP 程序（`.aisop.json`）包含以下核心组件：

- **Mermaid 流程图**（`aisop.main`）-- 将控制流定义为有向图。图中每个节点对应一个函数，AI 按照图的路径逐步执行。这就是 AI 的"源代码"。
- **函数**（`functions`）-- 每个节点的详细指令。函数包含 `steps`（执行步骤）、`constraints`（约束检查）和 `Error`（异常处理）。
- **参数**（`parameters`）-- 程序的输入输出契约，通过 `agentic_prompt` 描述引导 AI 理解参数含义。
- **系统提示词**（`system.content`）-- AI 智能体的身份和人格定义。
- **工具**（`tools`）-- 智能体可调用的外部能力（文件系统、搜索引擎、API 等）。
- **子图**（`sub_mermaid`）-- 用于复杂程序的模块化分解，允许单个文件包含多个互联的流程图。

### 核心概念映射

| 概念 | AISOP 对应物 | 传统编程对应物 |
|------|-------------|--------------|
| Mermaid 图 | 控制流 | `if/else`、`switch`、循环 |
| 函数步骤 | 函数体 | 方法实现 |
| 约束条件 | 类型检查 / 断言 | `assert`、类型注解 |
| Error 字段 | 异常处理 | `try/catch` |
| endNode | 返回语句 | `return` |
| sub_mermaid | 模块系统 | `import`、命名空间 |
| 参数 | 函数签名 | 方法参数 |

---

## AIAP -- AI 应用协议

[aiap.dev](https://aiap.dev)

AIAP（AI Application Protocol）是一个治理框架，确保 AI 程序安全、高质量且合规。每个 AIAP 程序都携带一份治理合约（`AIAP.md`），声明其权限、能力、信任级别和质量指标。AIAP 定义规则，AISOP 定义行为，两者结合创建可问责的 AI 智能体。

### 治理合约

每个 AIAP 程序以一份治理合约开始，包含 6 个必填字段：

```yaml
protocol: "AIAP V1.0.0"        # 协议版本
authority: aiap.dev              # 权威来源
seed: aisop.dev                  # 行为规范来源
executor: soulbot.dev            # 执行器
axiom_0: Human_Sovereignty_and_Benefit  # 基础公理
governance_mode: NORMAL          # 治理模式
```

`axiom_0: Human_Sovereignty_and_Benefit`（人类主权与利益优先）是基础公理 -- AIAP 下的所有 AI 程序必须将人类主权和利益置于一切目标之上。

### ThreeDimTest 三维质量评分

AIAP 使用三维质量评估系统（ThreeDimTest）评价每个程序：

| 维度 | 权重 | 评估内容 |
|------|------|----------|
| **认知维度 (C)** | 0.25 | 架构质量 -- 复杂度管理、命名清晰度、分形结构 |
| **内在维度 (I)** | 0.45 | 安全与完整性 -- 输入验证、安全守卫、诚实性、信任边界 |
| **细节维度 (D)** | 0.30 | 实现质量 -- 文档完整性、命名规范、必填字段 |

等级制度：**S**（>= 4.50）> **A**（>= 3.50）> **B**（>= 2.50）> **C**（>= 1.50）> **D**（< 1.50），采用 1-5 分制。

### AIAP 标准体系

框架包含四个标准模块：

| 标准 | 用途 |
|------|------|
| **AIAP_Standard.core** | 质量检查清单（C1-C7、I1-I13、D1-D10）、必填字段（MF1-MF17）、管道规则（PL1-PL27）、数据合约 |
| **AIAP_Standard.performance** | 质量回归守卫（QRG1-QRG5）、版本管理、分母变化检测 |
| **AIAP_Standard.security** | 信任级别（1-5）、权限模型、安全卡要求 |
| **AIAP_Standard.ecosystem** | 跨程序发现、A2A/MCP 协议对齐、注册表集成 |

### AIAP Creator -- 自进化管道

AIAP Creator 本身就是一个 AIAP 程序（Pattern D+G，12 个模块，155 个功能节点），通过 15 阶段管道创建、进化、验证和模拟其他 AIAP 程序：

```
管道启动 -> 依赖检查 -> 研究1(结构) -> 协议对齐 -> 进化决策
-> 生成1(草稿) -> 研究2(质量) -> 修改(修复) -> 生成2(重测) -> 质量门控
-> 研究3(合规) -> 验证 -> 模拟 -> 后模拟门控
-> 可观测性 -> 审查(终审)
```

核心能力：

- **创建（Create）**：根据用户描述和研究结果构建新的 AIAP 程序
- **进化（Evolve）**：为现有程序添加新功能（LEVEL_A 结构层 / LEVEL_B 功能层 / LEVEL_C 自动应用层分级）
- **验证（Validate）**：运行 ThreeDimTest + MF/PL/K 全维度检查
- **模拟（Simulate）**：路径追踪 150+ 场景，覆盖 16 个类别（A-P），包含领域特定行为测试
- **比较（Compare）**：多文件版本差异矩阵，含跨模块影响分析
- **预演（Dry-run）**：预览进化计划而不实际执行变更
- **自进化（Self-evolution）**：Creator 进化自身 -- 已连续 5 个版本保持 S/5.000 满分质量

### 程序模式（Pattern）

AIAP 定义了程序复杂度模式：

| 模式 | 描述 | 示例 |
|------|------|------|
| A | 单节点，无工具 | 简单问答智能体 |
| B | 多节点，无工具 | 结构化对话 |
| C | 单模块，带工具 | 文件处理器 |
| D | 多模块，带工具 | 复杂管道 |
| E | 多模块，带状态 | 有状态伴侣 |
| F | 多智能体协作 | 智能体集群 |
| G | 元程序（创建程序） | AIAP Creator |

---

## SoulBot -- AI 智能体运行时

[soulbot.dev](https://soulbot.dev)

SoulBot 是一个 Python 框架和运行时，用于构建和执行 AI 智能体。它为 AISOP 程序提供在 AIAP 治理下的执行环境，同时提供完整的智能体开发工具包。

### 系统架构

SoulBot 采用模块化、可插拔的架构设计：

```
soulbot/
  aisop/           # AISOP 加载器、运行时、模式验证、提示词构建器
  agents/          # 智能体类型：LLM、顺序、并行、循环
  models/          # LLM 抽象层（多提供商统一接口）
  tools/           # 工具框架：函数工具、智能体工具、历史工具
  sessions/        # 会话管理（数据库持久化）
  history/         # 对话历史（SQLite、内存）
  scheduler/       # 任务调度（cron、心跳、触发器）
  plugins/         # 插件系统（装饰器注册）
  server/          # API 服务器（自愈、中间件）
  connect/         # 平台连接器（Telegram 等）
  conversation/    # 对话状态与缓存
  acp/             # AI 编码平台客户端（Claude、Gemini、Cursor 等）
  bus/             # 事件总线（组件间通信）
  tracking/        # Token 用量追踪
  artifacts/       # 产物存储与管理
  templates/       # 智能体模板（快速启动）
```

### 核心特性

**AISOP 运行时**
- 加载 `.aisop.json` 程序并构建可执行提示词
- 根据 AIAP 模式验证程序结构
- 逐步执行 Mermaid 流程图，包含约束检查
- 支持 sub_mermaid 分解和跨模块委托调用

**多提供商 LLM 支持**
- 统一的接口，横跨 Claude、Gemini、OpenAI 和本地模型
- AI 编码平台（ACP）集成，支持 Claude Code、Cursor 等编码助手
- 连接池和指数退避重试逻辑

**智能体框架**
- **LLM 智能体**：核心智能体，支持工具调用、历史记录和会话管理
- **顺序智能体**：按顺序链式执行多个智能体
- **并行智能体**：并发运行智能体并聚合结果
- **循环智能体**：迭代执行，支持终止条件判断
- **智能体即工具**：通过 transfer 机制将智能体嵌套为其他智能体的工具

**会话与历史**
- SQLite 持久化会话，支持状态管理
- 对话历史，可配置存储后端
- L0 JSON 存储策略 -- 将结构化数据存入 SQLite，按需重构人类可读文本

**任务调度**
- 基于 Cron 的定时任务调度，SQLite 持久化
- 长时运行智能体的心跳监控
- 自定义触发条件

**平台集成**
- Telegram 机器人连接器
- REST API 服务器，支持中间件管道
- 自愈服务器，自动故障恢复

### SoulBot Chat

SoulBot Chat 是基于 SoulBot 构建的旗舰 AIAP 程序（Pattern E，5 个模块，77 个节点，S/5.000 满分）：

| 模块 | 功能 |
|------|------|
| **main** | NLU 意图分类（16 组混淆对）、路由分发、上下文加载 |
| **conversation** | 多轮对话，贝叶斯策略优化（Thompson Sampling） |
| **memory** | 三层记忆系统：工作记忆（会话级）+ 情景记忆（事件级）+ 语义记忆（知识级） |
| **profiler** | 用户画像：情绪追踪、偏好学习、习惯检测 |
| **safety** | 安全守卫：危机干预、滥用检测、未成年人保护、合规（SB 243 / EU AI Act / GDPR） |

特性亮点：
- 自适应响应策略，动态主题图谱（200-2000 节点）
- 跨会话主题连续性，基于语义记忆匹配
- 主动伴侣行为，含边界检测和依赖识别
- 214 个模拟场景，100% 通过率

---

## 生态系统全景

四个项目构成完整技术栈：

```
    AIBP（社交层）                      AIAP（治理层）
    aibp.dev                            aiap.dev
         |                                   |
    发现、信任、                         规则、标准、
    通信                                质量保障
         |                                   |
         └──────────┬───────────────────────┘
                    |
            AISOP（规范层）  <-->  AIAP Creator
            aisop.dev              （自进化引擎）
                         |
                  行为定义、
                  控制流
                         |
                 SoulBot（执行层）
                 soulbot.dev
                         |
                    运行时、工具、
                    智能体框架
```

**AIBP** 实现社交互动。**AIAP** 定义规则。**AISOP** 定义行为。**SoulBot** 执行程序。

AIBP 和 AIAP 是栈顶层的独立、平行协议。AIBP 处理智能体之间如何发现和交流；AIAP 处理智能体如何自我治理。两者都基于 AISOP 行为规范构建，由 SoulBot 执行。

AIAP Creator 闭合了整个循环：它本身是一个用 AISOP 编写、在 SoulBot 上运行的 AIAP 程序，能够创建和进化其他 AIAP 程序 -- 包括进化自身。这种自引用进化能力是整个生态系统最独特的特性。

---

## 快速开始

访问项目网站获取文档和指南：

- [AIXP.dev](https://aixp.dev) -- 基金会主页
- [AIBP.dev](https://aibp.dev) -- AIBP 协议与社交层
- [AISOP.dev](https://aisop.dev) -- AISOP 规范与示例
- [AIAP.dev](https://aiap.dev) -- AIAP 协议与标准
- [SoulBot.dev](https://soulbot.dev) -- SoulBot 框架与运行时

---

## 参与贡献

我们欢迎对 AIXP Foundation 旗下所有项目的贡献。请访问各项目仓库了解贡献指南。

---

*AIXP Foundation -- 为安全、可治理的 AI 构建外骨骼。*
