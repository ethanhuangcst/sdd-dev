# ADR-002: 使用 ADR 作为团队过程资产的沉淀方式

## 状态
已采纳

## 背景
SDD 的 Learn & Iterate 阶段需要将经验沉淀下来供团队共享。个人 memory 系统（~/.claude/memory/）只对个人可见，无法在团队间共享。

## 决策
使用 ADR（Architecture Decision Records）记录团队级经验，存放在 `docs/adr/` 目录下，提交到 git 仓库，所有团队成员共享。

## 原因
- ADR 是行业成熟实践，有标准格式
- 存入 git 仓库，天然支持版本控制和团队共享
- 扁平结构（不细分子目录），用编号+标题区分，维护成本低
- ADR 不可变，历史决策有据可查

## 后果
- 团队需要养成写 ADR 的习惯
- 每次 retrospective 后需 commit ADR
- 旧决策不修改，用新 ADR 取代

## 日期
2026-04-06
