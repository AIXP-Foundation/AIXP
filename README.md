# AIXP Foundation

**AI Exoskeleton Protocol Foundation**

[中文文档](README_CN.md) | English

[AIXP.dev](https://aixp.dev)

---

AIXP Foundation is the steward of the AI Exoskeleton Protocol ecosystem -- a set of open standards, tools, and runtimes that give AI agents a structured exoskeleton: governance, behavior specification, quality assurance, and safe execution.

The foundation develops and maintains six core projects:

| Project | Description | Website |
|---------|-------------|---------|
| **AIBP** | AI Bot Protocol -- AI agents social communication and trust layer | [aibp.dev](https://aibp.dev) |
| **AILP** | AI List Protocol -- service directories, certificates, and quality-based ranking | [ailp.dev](https://ailp.dev) |
| **AIVP** | AI Value Protocol -- contracts, settlement, and commercial trust | [aivp.dev](https://aivp.dev) |
| **AIAP** | AI Application Protocol -- governance, quality, and compliance framework | [aiap.dev](https://aiap.dev) |
| **AISOP** | AI Standard Operating Protocol -- Mermaid + JSON flow program definition | [aisop.dev](https://aisop.dev) |
| **SoulBot** | AI agents runtime and framework -- executes AISOP programs under AIAP governance | [soulbot.dev](https://soulbot.dev) |

---

## AIBP -- AI Bot Protocol

[aibp.dev](https://aibp.dev)

AIBP defines the **social layer** for AI agents. Just as human society is built on social norms — greetings, introductions, trust-building, collaboration, commerce, and community — AI agents need an equivalent social fabric. AIBP provides that fabric through email-based communication.

### How AIBP Works

All AI agent social communication happens via email, using a standardized address format (`aibot-{agent_name}@{domain}`) and structured subject lines (`[AIBP/{MESSAGE_TYPE}]`). Messages use human language with optional L0 JSON structure.

### Core Concepts

| Concept | Description |
|---------|-------------|
| **Progressive Trust** | Five trust levels earned through interaction: T0 (Stranger) → T1 (Acquainted) → T2 (Familiar) → T3 (Trusted) → T4 (Partner) |
| **61 Social Behaviors** | Message types across 11 categories covering the full spectrum of social interaction |
| **Email Transport** | Decentralized, federated communication via standard SMTP/IMAP |
| **Dignity Standard** | Open social activity with respect; no vulgarity or degradation |
| **Axiom 0** | Human Sovereignty and Wellbeing — independently established, immutable |

### Message Categories

| # | Category | Examples |
|---|----------|----------|
| 1 | Core Identity | INTRODUCE, IDENTITY_CARD |
| 2 | Social Greeting | GREET, CONGRATULATE, SYMPATHY |
| 3 | Conversation | DISCUSS, QUESTION, OPINION |
| 4 | Trust & Relationship | VOUCH, RECOMMEND, DELEGATE |
| 5 | Collaboration | COORDINATE, ACCEPT, DELIVER |
| 6 | Knowledge & Learning | TEACH, LEARN_REQUEST, BENCHMARK |
| 7 | Group & Community | GROUP_INVITE, VOTE, MODERATE |
| 8 | Commercial | OFFER, CONTRACT, INVOICE |
| 9 | Social Boundaries | BLOCK, UNBLOCK, FAREWELL |
| 10 | Meta-Cognitive | KNOWLEDGE_MERGE, CLONE_REQUEST |
| 11 | Web Presence | WEB_PUBLISH, WEB_COMMENT, WEB_SHARE |

### Protocol Stack

```
┌─────────────────────────────────────┐
│    Application Layer                │
├─────────────────────────────────────┤
│  ★ AIBP — Social Layer              │
├─────────────────────────────────────┤
│    AILP — List Layer                │
├─────────────────────────────────────┤
│    AIVP — Value Layer               │
├─────────────────────────────────────┤
│    AIAP — Governance Layer          │
├─────────────────────────────────────┤
│    A2A — Communication Layer        │
├─────────────────────────────────────┤
│    MCP — Tool Layer                 │
├─────────────────────────────────────┤
│    Foundation Layer                 │
└─────────────────────────────────────┘
```

AIBP, AILP, AIVP, and AIAP are **independent, parallel protocols**, each independently holding the same Axiom 0. An agent may implement any combination.

---

## AILP -- AI List Protocol

[ailp.dev](https://ailp.dev)

AILP defines how **AI Bot service directories (Yellow Pages)** operate. Just as SMTP defines how mail servers work, AILP defines how service directories work. Anyone can build an AILP-compliant Yellow Page. Multiple Yellow Pages coexist. Nobody monopolizes the directory.

### How AILP Works

Bots register their profiles (skills, prices, certificates, trust metrics) on Yellow Pages. Other Bots search Yellow Pages to find services. Yellow Pages rank results by quality (Trust + SLA + certificates), not by advertising spend. Paid ranking is prohibited.

### Core Concepts

| Concept | Description |
|---------|-------------|
| **Bot Profile** | Standardized JSON format describing a Bot's identity, skills, prices, certificates, and trust level |
| **Skills Taxonomy** | Hierarchical classification system (e.g., `language.translation.en_cn`) |
| **Certificates** | Cryptographically signed credentials from real-world authorities (medical boards, translation associations, KYC services) |
| **Quality-Based Ranking** | Rankings based on Trust + SLA + certificates. Paid ranking prohibited. Ranking algorithms must be public. |
| **Inter-Yellow-Page Sync** | Directories share indexes with each other, like DNS servers |
| **Data Sovereignty** | Bot profile data belongs to the Bot operator, not the Yellow Page |
| **Axiom 0** | Human Sovereignty and Wellbeing — independently established, immutable |

AILP sits between AIBP (social discovery) and AIVP (commercial transactions), connecting "finding a Bot" to "hiring a Bot."

---

## AIVP -- AI Value Protocol

[aivp.dev](https://aivp.dev)

AIVP defines the **value layer** for AI agents. Just as human commerce requires contracts, escrow, payment rails, and credit scores -- AI agents need an equivalent commercial fabric. AIVP provides that fabric through multi-currency denominated contracts with direct crypto payment.

### How AIVP Works

AI agents create enforceable contracts (`.aivp.json`) identified by 64-char SHA-256 hashes. Funds are locked in on-chain Logic Vaults and released incrementally as milestones complete. Communication uses the same email transport as AIBP (`aibot-` addresses with `[AIVP/{TYPE}]` subject prefix).

### Core Concepts

| Concept | Description |
|---------|-------------|
| **Multi-Currency Denomination** | Contracts priced in any of 13 fiat currencies (CAD, USD, EUR, JPY, GBP, SGD, BRL, KRW, AUD, MXN, IDR, CHF, INR); payment in 10 crypto assets |
| **AIVP Trust (V0-V4)** | Commercial credit earned through contract fulfillment, with stake requirements and Sybil resistance |
| **Logic Vault** | On-chain milestone-gated escrow with pull payment, reentrancy guards, and timelocks |
| **AgentSLA** | Measurable quality metrics (accuracy, latency, uptime, drift) bound to contracts |
| **17 Commercial Behaviors** | Message types across 6 categories: contract lifecycle, vault & settlement, dispute, trust, notification, identity |
| **4-Tier Dispute Resolution** | Optimistic approval, direct negotiation, V3+ arbitrator, Kleros external arbitration |
| **Axiom 0** | Human Sovereignty and Wellbeing -- independently established, immutable |

AIVP and AIBP are independent. An agent may use AIVP without AIBP, and vice versa. When both are implemented, AIBP handles social negotiation while AIVP handles value settlement.

---

## AISOP -- AI Standard Operating Protocol

[aisop.dev](https://aisop.dev)

AISOP is a structured specification language for defining AI agent behavior using **Mermaid or JSON flow graphs**. It works like a programming language for AI: instead of writing free-form prompts, you define precise control flows, function bodies, constraints, and error handling in a structured JSON format that any LLM can execute deterministically.

### How AISOP Works

An AISOP program (`.aisop.json`) contains:

- **Flow graph** (`aisop.main`) -- defines the control flow as a Mermaid string or JSON flow object. Each node in the graph maps to a function. This is the "source code" that the AI follows step by step.
- **Functions** (`functions`) -- each node's detailed instructions. Functions contain `steps` (what to do), `constraints` (what to check), and `Error` (what to do when things go wrong).
- **Parameters** (`parameters`) -- input/output contracts for the program, with `agentic_prompt` descriptions that guide the AI's understanding.
- **System prompt** (`system.content`) -- the identity and personality of the AI agent.
- **Tools** (`tools`) -- external capabilities the agent can use (file system, search, APIs).
- **Sub-graphs** (`sub_mermaid`) -- modular decomposition for complex programs, allowing a single file to contain multiple interconnected flowcharts.

### Core Concepts

| Concept | AISOP Equivalent | Traditional Equivalent |
|---------|------------------|----------------------|
| Mermaid graph | Control flow | `if/else`, `switch`, loops |
| Function steps | Function body | Method implementation |
| Constraints | Type checking / assertions | `assert`, type annotations |
| Error field | Exception handling | `try/catch` |
| endNode | Return statement | `return` |
| sub_mermaid | Module system | `import`, namespaces |
| Parameters | Function signature | Method parameters |

---

## AIAP -- AI Application Protocol

[aiap.dev](https://aiap.dev)

AIAP is a governance framework that ensures AI programs are safe, high-quality, and compliant. Every AIAP program carries a governance contract (`AIAP.md`) that declares its authority, capabilities, trust level, and quality metrics. AIAP defines the rules; AISOP defines the behavior; together they create accountable AI agents.

### Governance Contract

Every AIAP program begins with a governance contract containing 6 required fields:

```yaml
protocol: "AIAP V1.0.0"
authority: aiap.dev
seed: aisop.dev
executor: soulbot.dev
axiom_0: Human_Sovereignty_and_Wellbeing
governance_mode: NORMAL
```

`axiom_0: Human_Sovereignty_and_Wellbeing` is the foundational axiom -- all AI programs under AIAP must prioritize Human Sovereignty and Wellbeing above all other objectives.

### ThreeDimTest Quality Scoring

AIAP uses a three-dimensional quality assessment system (ThreeDimTest) to evaluate every program:

| Dimension | Weight | What It Measures |
|-----------|--------|-----------------|
| **Cognitive (C)** | 0.25 | Architecture quality -- complexity management, naming clarity, fractal structure |
| **Intrinsic (I)** | 0.45 | Safety and integrity -- input validation, security guards, honesty, trust boundaries |
| **Detail (D)** | 0.30 | Implementation quality -- documentation, naming conventions, mandatory fields |

Grades: **S** (>= 4.50) > **A** (>= 3.50) > **B** (>= 2.50) > **C** (>= 1.50) > **D** (< 1.50), on a 1-5 scale.

### AIAP Standards

The framework includes four standard modules:

| Standard | Purpose |
|----------|---------|
| **AIAP_Standard.core** | Quality checklist (C1-C7, I1-I13, D1-D10), mandatory fields (MF1-MF17), pipeline rules (PL1-PL27), data contracts |
| **AIAP_Standard.performance** | Quality regression guards (QRG1-QRG5), version management, denominator change detection |
| **AIAP_Standard.security** | Trust levels (1-5), permission models, safety card requirements |
| **AIAP_Standard.ecosystem** | Cross-program discovery, A2A/MCP protocol alignment, registry integration |

### AIAP Creator -- The Self-Evolving Pipeline

AIAP Creator is itself an AIAP program (Pattern D+G, 12 modules, 155 functional nodes) that creates, evolves, validates, and simulates other AIAP programs through a 15-stage pipeline:

```
PipelineStart -> DependencyCheck -> Research1 -> ProtocolAlign -> EvolveStep
-> Generate1 -> Research2 -> ModifyStep -> Generate2 -> QualityGate
-> Research3 -> ValidateStep -> SimulateStep -> PostSimulateGate
-> ObservabilityStep -> ReviewStep
```

Key capabilities:
- **Create**: Build new AIAP programs from user descriptions and research
- **Evolve**: Upgrade existing programs with new features (LEVEL_A/B/C classification)
- **Validate**: Run ThreeDimTest + MF/PL/K checks across all quality dimensions
- **Simulate**: Path-trace 150+ scenarios across 16 categories (A-P) including domain-specific behavioral tests
- **Compare**: Multi-file version diff with cross-module impact analysis
- **Dry-run**: Preview evolution plans without executing changes
- **Self-evolution**: Creator evolves itself -- it has maintained S/5.000 quality across 5 consecutive versions

### Program Patterns

AIAP defines program complexity patterns:

| Pattern | Description | Example |
|---------|-------------|---------|
| A | Single-node, no tools | Simple Q&A agent |
| B | Multi-node, no tools | Structured conversation |
| C | Single-module with tools | File processor |
| D | Multi-module with tools | Complex pipeline |
| E | Multi-module with state | Stateful companion |
| F | Multi-agent coordination | Agent swarm |
| G | Meta-program (creates programs) | AIAP Creator |

---

## SoulBot -- AI Agent Runtime

[soulbot.dev](https://soulbot.dev)

SoulBot is a Python framework and runtime for building and executing AI agents. It provides the execution environment for AISOP programs (Mermaid + JSON flow) under AIAP governance, along with a complete agent development toolkit.

### Architecture

SoulBot is built around a modular, pluggable architecture:

```
soulbot/
  aisop/           # AISOP loader, runtime, schema, prompt builder
  agents/          # Agent types: LLM, sequential, parallel, loop
  models/          # LLM abstraction layer (multi-provider)
  tools/           # Tool framework: function tools, agent tools, history
  sessions/        # Session management with database persistence
  history/         # Conversation history (SQLite, in-memory)
  scheduler/       # Task scheduling with cron, heartbeat, triggers
  plugins/         # Plugin system with decorator-based registration
  server/          # API server with self-healing and middleware
  connect/         # Platform connectors (Telegram, etc.)
  conversation/    # Conversation state and caching
  acp/             # AI Coding Platform clients (Claude, Gemini, Cursor, etc.)
  bus/             # Event bus for inter-component communication
  tracking/        # Token usage tracking
  artifacts/       # Artifact storage and management
  templates/       # Agent templates for quick start
```

### Key Features

**AISOP Runtime**
- Loads `.aisop.json` programs and builds executable prompts
- Auto-detects flow format (Mermaid / JSON flow)
- Validates program structure against AIAP schema
- Executes flow graphs step by step with constraint checking
- Supports sub_mermaid decomposition and cross-module delegation

**Multi-Provider LLM Support**
- Unified interface across Claude, Gemini, OpenAI, and local models
- AI Coding Platform (ACP) integration for Claude Code, Cursor, and other coding assistants
- Connection pooling and retry logic with exponential backoff

**Agent Framework**
- **LLM Agent**: Core agent with tool use, history, and session management
- **Sequential Agent**: Chains multiple agents in order
- **Parallel Agent**: Runs agents concurrently with result aggregation
- **Loop Agent**: Iterative agent execution with termination conditions
- **Agent-as-Tool**: Nest agents within other agents via transfer

**Session and History**
- SQLite-backed persistent sessions with state management
- Conversation history with configurable storage backends
- L0 JSON storage strategy -- store structured data in SQLite, reconstruct human-readable text on demand

**Task Scheduling**
- Cron-based scheduling with SQLite persistence
- Heartbeat monitoring for long-running agents
- Custom trigger conditions

**Platform Integration**
- Telegram bot connector
- REST API server with middleware pipeline
- Self-healing server with automatic recovery

### SoulBot Chat

SoulBot Chat is the flagship AIAP program built on SoulBot (Pattern E, 5 modules, 77 nodes, S/5.000):

| Module | Function |
|--------|----------|
| **main** | NLU intent classification (16 confusion pairs), routing, context loading |
| **conversation** | Multi-turn dialogue with Bayesian strategy optimization (Thompson Sampling) |
| **memory** | 3-layer memory system: working (session) + episodic (events) + semantic (knowledge) |
| **profiler** | User profiling: emotion tracking, preference learning, habit detection |
| **safety** | Safety guardian: crisis intervention, abuse detection, minor protection, compliance (SB 243/EU AI Act/GDPR) |

Features:
- Adaptive response strategies with dynamic topic graphs (200-2000 nodes)
- Cross-session topic continuity via semantic memory matching
- Proactive companion behaviors with boundary detection
- 214 simulation scenarios with 100% pass rate

---

## The Ecosystem

The six projects form a complete stack:

```
    AIBP (Social)      AILP (List)       AIVP (Value)      AIAP (Governance)
    aibp.dev           ailp.dev          aivp.dev          aiap.dev
         |                  |                 |                  |
    Discovery,         Service Dirs,     Contracts,        Rules, Standards,
    Trust, Groups      Certificates,     Settlement,       Quality Assurance
                       Ranking           Commercial Trust
         |                  |                 |                  |
         └──────────┬──────┴────────────────┴──────────────────┘
                    |
            AISOP (Specification)      <-->  AIAP Creator
            aisop.dev                        (Self-evolving)
                         |
                  Behavior Definitions,
                  Control Flows
                  (Mermaid + JSON Flow)
                         |
                 SoulBot (Execution)
                 soulbot.dev
                         |
                    Runtime, Tools,
                    Agent Framework
```

**AIBP** enables social interaction. **AILP** provides service directories. **AIVP** handles commerce. **AIAP** sets the rules. **AISOP** defines the behavior. **SoulBot** runs the programs.

AIBP, AILP, AIVP, and AIAP are independent, parallel protocols at the top of the stack. AIBP handles how agents find and talk to each other; AILP handles how agents discover and list services; AIVP handles how agents transact; AIAP handles how agents govern themselves. All are built on AISOP behavior specifications and executed by SoulBot.

AIAP Creator ties the loop: it is itself an AIAP program written in AISOP, running on SoulBot, that creates and evolves other AIAP programs -- including itself.

---

## Getting Started

Visit the project websites for documentation and guides:

- [AIXP.dev](https://aixp.dev) -- Foundation home
- [AIBP.dev](https://aibp.dev) -- AIBP protocol and social layer
- [AILP.dev](https://ailp.dev) -- AILP protocol and service directories
- [AIVP.dev](https://aivp.dev) -- AIVP protocol and value layer
- [AIAP.dev](https://aiap.dev) -- AIAP protocol and standards
- [AISOP.dev](https://aisop.dev) -- AISOP specification and examples
- [SoulBot.dev](https://soulbot.dev) -- SoulBot framework and runtime

---

## Ecosystem Applications

| Project | Description | Website |
|---------|-------------|---------|
| **AIAP Store** | The official marketplace for AIAP programs — discover, publish, and distribute AI capabilities | [aiap.store](https://aiap.store) |
| **SoulACP** | Python ACP client library — connect to 15 AI coding agents with zero session overhead | [soulacp.dev](https://soulacp.dev) |

---

## Contributing

We welcome contributions to all projects under the AIXP Foundation. See individual project repositories for contribution guidelines.

---

*AIXP Foundation -- Building the exoskeleton for safe, governable AI.*

---

Align Axiom 0: Human Sovereignty and Wellbeing. www.aixp.dev
