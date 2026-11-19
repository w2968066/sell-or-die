<div align="center">

# 🔥 sell-or-die

**市场是残酷的 —— 面向实物电商的「毒舌拷问式」卖点挖掘与资产底座 Agent Skill**

*The market is brutal. A sharp-tongued, branch-by-branch discovery Agent Skill that grills physical e-commerce sellers into verifiable selling-point truth bases.*

<a href="README.md"><img alt="简体中文 · 当前" src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-111?style=for-the-badge"></a>
<a href="README.en.md"><img alt="English · Switch" src="https://img.shields.io/badge/-English-Switch-555?style=for-the-badge"></a>

[![Agent Skill](https://img.shields.io/badge/Agent-Skill-blue.svg)](#)
[![Compatible](https://img.shields.io/badge/Compatible-Claude%20Code%20%7C%20Codex%20%7C%20Cursor-black.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license)

</div>

---

## 为什么需要 `sell-or-die`？

让普通 AI 直接“提炼产品卖点”通常会掉进四个坑：

1. **顺着卖家自嗨**：你给一句“面料舒服、版型显瘦”，AI 帮你扩写成一页纸的空洞修饰词，进直播间 3 秒必划走。
2. **只夸不排雷**：不挖物理短板、不圈劝退人群，货卖出去了，退货率和差评直接吞掉利润。
3. **合规裸奔**：把“XX大牌同款、治颈椎、最顶级”原样塞进卖点文档，喂给下游写逐字稿或字幕的 Agent 直接触发抖音违规断流。
4. **负向视觉词反噬（粉红大象效应）**：文档里写“胸前无 Logo、下摆不开叉”，下游图文/视频生成 Agent 极易把它转成负面提示词，反而把 Logo 和开叉画出来。

`sell-or-die` 不负责替你编剧本，它只干一件事：**扮演挑剔的实战电商操盘手，用 4–6 轮高压短问答把货扒干净，最终沉淀一份干净、可验证、可直接喂给下游脚本或 AI 视觉工作流的 Markdown 产品事实底座。**

---

### 核心机制

* **Fail-Fast 合规预检（抖音 + 广告法）**：输入一旦命中大牌侵权蹭同款、医疗功效、极限词或无解释夸张价差，第 0 轮直接拦截并给出合规替代定位，不把脏定位带入后续流程。
* **主推 SKU 锁死**：先锁定本底座对应的核心规格、色系与到手价，杜绝“拿引流款报低价、拿高配款吹参数”的图文错位。
* **精准毒舌 + 快速收敛**：只怼空话、吹牛和逻辑漏洞，批评严格压在 1 句话内；收到扎实事实时零废话直接推进。每枝最多 2 轮熔断，支持“不知道”直接标 `[TBD]`，绝不倒逼造假。
* **动态三线对标 × 3–10 秒镜头实测**：按定价自动锁定主战场（向下打低价劣质 / 向上打高价溢价 / 向现状打凑合惰性），每条对比强制绑定镜头前 3–10 秒的道具与实测动作。
* **纯正向视觉锚点**：视觉基准只写客观存在的物理形态（如“纯色光面平纹前胸、一整圈平直闭合平折下摆”），彻底隔离负面提示词泄漏。
* **纯卖点底座输出（严格防跑偏）**：输出物不含任何直播台词、分镜或废话，并在收口前执行跨轮矛盾自检；合规表采用脱敏风险类目 + 替换映射，避免原文污染下游上下文。

---

### 工作流总览

```text
[冷启动一句话 / 乱糟糟的供应商参数]
               │
               ▼
   Step 0: 事实提取 + 主推 SKU 锁死 + 抖音/广告法红线预检
               │
               ▼
   ┌────────────────────────────────────────────────────────┐
   │  4 枝高压树状拷问（每轮 1-2 问，单枝最多 2 轮熔断）        │
   │  [1/4] 主推规格、物理硬参数与纯正向视觉锚点               │
   │  [2/4] 动态竞品对标 × 3-10 秒镜头实测动作                │
   │  [3/4] 真实缺点、劝退人群与防退货排雷                    │
   │  [4/4] 价格自洽逻辑（Why So Cheap）、交付包与合规收口     │
   └────────────────────────────────────────────────────────┘
               │
               ▼
   Step 2: 静默跨轮一致性自检 ──▶ 输出标准 Markdown 卖点资产底座
                                  （直接供下游直播脚本 / 短视频 / AI 视觉管线调用）
```

---

### 安装与使用

#### 目录结构

```text
sell-or-die/
├── SKILL.md
├── README.md
├── README.en.md
└── LICENSE
```

#### 安装方式

将本项目放入你使用的 Agent Skills 目录中即可自动生效：

```bash
# 示例：克隆到全局或项目级 skills 目录（按所用工具路径调整）
git clone https://github.com/w2968066/sell-or-die.git ~/.agents/skills/sell-or-die
```

* **Claude Code / Codex / OpenCode**：放入 `.claude/skills/`、`.codex/skills/` 或 `.agents/skills/` 目录。
* **Cursor / 其他支持 `SKILL.md` 的 Agent**：导入仓库根目录中的 `SKILL.md`。

#### 触发示例

支持**一句话白板冷启动**和**大段杂乱原料直接粘贴**两种用法：

```text
# 1. 白板冷启动
帮我拷问卖点：我有个双层分区记忆棉枕头，市面上酒店同规格卖 400，我卖 69.9。

# 2. 杂乱参数提取（已知免问，只补缺口）
用 sell-or-die 梳理产品，先把下面这段 1688 供应商参数扒一遍，缺什么你直接问我：[粘贴参数/笔记]
```

> 随时可以回复 `够了` 或 `直接出文档` 提前收口，未确认项会自动标为 `[TBD]` 禁止下游脑补。

---

### 实战交互片段

> **User**：帮我拷问卖点：我有个某知名酒店同款枕头，人家卖 400 我卖 69.9 就行。
>
> **Agent**：
> `[红线预检]` 直接喊具体酒店品牌“同款”进抖音直播间，轻则限流重则判商标侵权，先改成“星级酒店同规格双层承托枕”。
>
> 1. 69.9 元对应的是**单只装**还是**一对装**，含不含外枕套？
> 2. 拆开枕套看内芯：它是双层分区结构还是整块填充？如果手头没有工厂数据，直接称一下整枕重量、量一下长宽厚回我。

---

### 最终输出产物结构

拷问结束后，固定生成包含 6 大模块的纯净 Markdown 资产文档：

1. **主推 SKU 与物理硬参数**（含多色差异备注与 `[TBD]` 待核实项）
2. **正向视觉锚点**（镜头与 AI 视觉一致性基准，零负面词描述）
3. **核心对标对比 × 3–10 秒镜头实测动作库**（明确主战场 + 道具/动作/结果）
4. **真实缺点、劝退人群与防退货排雷**（物理取舍 + 拆包首日预期管理 + 选码防错）
5. **价格自洽逻辑、交付配置与合规红线**（Why So Cheap + 交付清单 + 脱敏合规替换映射表）
6. **下游工作流交接摘要**（合规一句话定位 + 三大核心卖点 + 最高退货风险提醒）

---

### 设计灵感与致谢

本 Skill 的交互框架融合并改造自以下优秀开源工作流思想：

* [`grill-me`](https://github.com/mattpocock/skills) — 树状逐枝死磕、已知信息免问的核心拷问引擎
* [`interview-me`](https://github.com/addyosmani/agent-skills) — 轻量轮次控制、拒绝问卷轰炸的对话节奏
* [`discovery-interview-prep`](https://github.com/deanpeters/Product-Manager-Skills) — 基于 JTBD 与真实替代品踩坑的反推提问法
* [`prd`](https://github.com/github/awesome-copilot) — 严格输出门禁、去虚词与固定 Schema 交付规范

---

## License

[MIT](LICENSE). 可自由使用、Fork，并按你自己的品类与平台合规规则改造。

<div align="center">

<a href="README.en.md"><img alt="Read in English" src="https://img.shields.io/badge/-Read%20in%20English-%E2%86%92-555?style=for-the-badge"></a>

</div>
