# AI Project Constitution Template

这是一套可复用的 AI 项目宪法模板，用于约束 Skill、Agent、AI 工作流、CLI/IDE 适配项目。

核心原则：

> AI 扩展搜索空间，人类压缩决策空间，脚本验证确定性空间，Skill 保存可复用判断。

## 推荐使用方式

把本目录复制到你的项目根目录，然后根据项目类型修改以下文件：

```text
CONSTITUTION.md        # 项目最高原则
DECISION_RIGHTS.md     # 人类与 AI 的决策权边界
ROADMAP.md             # 路线图边界与功能准入
SKILL_POLICY.md        # Skill 准入、拆分、加载、修改规则
GOTCHAS.md             # 失败案例与反模式沉淀
evals/                 # 测试用例模板
```

## 最小落地版本

如果你的项目还很小，只保留这三个文件也可以：

```text
CONSTITUTION.md
DECISION_RIGHTS.md
GOTCHAS.md
```

## 适用项目

- AI Skill 项目
- Agent 工作流项目
- AI 编程约束系统
- 面试 / 学习 / 写作 / 投研类流水线
- 多 CLI / IDE 适配项目
- 需要防止 AI 自主膨胀的工具系统

## 不适用场景

- 一次性 prompt
- 临时问答
- 无法定义输入输出的探索性聊天
- 没有验收标准的创意发散
