# ADR-001: 采用 Spec-Driven Development (SDD) 工作流

## 状态
已采纳

## 背景
传统 Vibe Coding 缺乏规格约束，导致 AI 生成的代码难以验证、文档与代码脱节、团队协作困难。需要一套结构化的 AI 辅助开发流程。

## 决策
采用 SDD 工作流：Plan → Spec → Develop → Verify → Learn & Iterate。每个功能开发前必须先完成三份规格文档（需求规格、设计规格、UI规格），再进行 TDD 开发，最后通过 DoD 验收。

## 原因
- Spec 先行确保 AI 理解需求，减少返工
- TDD 确保代码质量和可测试性
- DoD 提供明确的完工标准
- 相比纯 Vibe Coding，可验证性更强

## 后果
- 开发前置成本增加（写规格），但整体质量提升
- 需要团队掌握 ATDD、TDD 等技能
- 规格文档成为团队沟通的共同语言

## 日期
2026-04-06
