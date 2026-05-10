# Skill Policy

> 本文件定义什么时候该写 Skill，什么时候不该写 Skill，以及 Skill 如何修改。

---

## 1. 什么值得 Skill 化

满足以下条件，才值得 Skill 化：

| 条件 | 要求 |
|---|---|
| 高频重复 | 会反复使用 |
| 易错 | AI 或人类经常做错 |
| 有输入 | 能定义输入格式 |
| 有输出 | 能定义输出格式 |
| 可验证 | 有验收标准 |
| 有边界 | 能定义不做什么 |
| 有反例 | 能定义误触发情况 |
| 有人类判断 | 能固化人的 taste / 经验 |

---

## 2. 什么不应该 Skill 化

以下内容不应 Skill 化：

- 一次性聊天
- 临时脑暴
- 无法定义输入输出的任务
- 没有验收标准的任务
- 纯粹个人情绪宣泄
- 还没跑通的流程
- 只是为了“看起来系统化”的流程

---

## 3. Skill 必须包含

每个 Skill 至少包含：

```text
name
purpose
trigger
non-trigger
inputs
outputs
required_context
optional_context
procedure
validation
stop_conditions
human_decision_points
gotchas
```

---

## 4. Skill 修改流程

Skill 修改必须遵守：

```text
发现问题
  ↓
新增 gotcha 或 eval
  ↓
提出 patch
  ↓
跑测试
  ↓
人类 review
  ↓
合并
```

禁止：

- AI 自己修改核心 Skill 并自我批准
- 为了适配某个工具破坏核心规则
- 把新功能直接塞进已有 Skill，导致职责膨胀
- 没有反例测试就扩大触发条件

---

## 5. Skill 拆分原则

当一个 Skill 出现以下情况，应考虑拆分：

- 输出类型超过 2 类
- 触发条件变得模糊
- 需要读取过多上下文
- 产生多个互不相关的结果
- 验收标准无法统一
- 经常被误触发
- 开始同时承担规划、生成、审查、导出等职责

---

## 6. Skill 加载原则

优先短入口，按需加载重材料。

推荐：

```text
SKILL.md              # 只放触发、边界、流程摘要
references/*.md       # 放重规则、案例、长材料
scripts/*.py          # 放确定性执行逻辑
evals/*.yaml          # 放测试用例
```

禁止：

- 把所有知识都塞进一个巨大 SKILL.md
- 每次运行都加载全部上下文
- 为了“完整”牺牲触发精度
