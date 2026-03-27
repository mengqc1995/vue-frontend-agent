---
name: vue3-agents-pack
description: 在 Vue3 前端开发任务中应用内置 agents 规范包（页面、组件、API、路由、状态、样式、测试）。当用户提到 Vue3、页面开发、组件拆分、接口封装、Pinia、路由、样式规范时使用。
---

# Vue3 Agents 规范包

## 用途

- 为任意 Vue3 项目提供统一开发规范与技能步骤。
- 规范内容来源于本技能目录内置的 `agents/`，不依赖外部项目路径。

## 内置内容

- 规则索引：`agents/rules/README.md`
- 技能索引：`agents/skills/README.md`
- 规则目录：`agents/rules/`
- 技能目录：`agents/skills/`

## 使用流程

1. 先读取 `agents/rules/README.md` 与 `agents/skills/README.md`。
2. 按任务类型加载对应规则与技能文件。
3. 实现后按规则检查命名、结构、样式、测试与文档要求。

## 场景映射

- 新增页面：优先 `agents/skills/create-view/SKILL.md`
- 复杂页面拆分：补充 `agents/skills/vue-page-module/SKILL.md`
- 新增 API：`agents/skills/create-api/SKILL.md`
- 新增 Store：`agents/skills/create-store/SKILL.md`
- 创建组件：`agents/skills/create-component/SKILL.md`
- 主题样式：`agents/skills/theme-variables/SKILL.md`
