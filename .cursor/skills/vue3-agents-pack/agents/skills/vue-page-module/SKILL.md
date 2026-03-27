---
name: vue-page-module
description: >-
  参考 Vue3+TS 页面模块化目录约定组织 views 下页面（components、composables、types、constants 等）。
  在新增或重构多区块列表页/复杂页面、用户提到「页面目录结构」「与掘金规范一致」时使用；
  须结合页面体量与项目现有写法，避免为套模板而过度拆分。
---

# Vue 页面模块化目录（参考掘金 + 反教条）

## 参考来源

- [Vue3 + TypeScript 项目目录结构（掘金）](https://juejin.cn/post/7594351060615282707)：复杂页面可拆 `components/`、`composables/`，全局另有 `src/components`、`src/composables` 等分层思路。

本文档是**项目内对「单页目录」的实用摘要**，不是每条路由都必须满足的清单。

## 何时值得拆目录

**适合**在 `src/views/<模块>/` 下增加子结构的情况：

- 单文件 `index.vue` 已明显过长（逻辑 + 模板难以维护）。
- 有**可复用的页面内子组件**（表单区、表格区、抽屉等）。
- 有**可独立测试或复用的组合式逻辑**（列表请求、筛选、表格列配置等）。

**可以维持单文件**的情况：

- 简单 CRUD、几十～百余行内能说完。
- 与**同模块其它页面**风格一致更重要（不要这一页「微型架构」、隔壁页一大坨）。

## 推荐形态（按需取用）

在 `views/<page>/` 下可按需出现：

| 路径 | 用途 |
|------|------|
| `index.vue` | 页面入口：布局、拼装子组件、尽量少写业务细节 |
| `components/` | **仅本页使用**的 UI 块 |
| `composables/` | `useXxx()`：数据、副作用、与组件解耦的逻辑 |
| `types.ts` 或 `types/` | 本页专用类型；体量小用单文件即可 |
| `constants/` 或 `constants.ts` | 码表、下拉选项；注意 **TypeScript 循环依赖**（例如 `types` 需 `typeof` 某常量时，勿让 `constants` 入口反向依赖 `types` 全量） |
| `styles/` 或同目录 `scss` | 样式较多时再抽；否则 **scoped 写在 `.vue` 里完全合理** |

**不必**为了「对齐文章」强行建空目录或把 10 行常量拆成三个文件。

## 避免教条主义（必看）

1. **目录数量 ∝ 页面复杂度**：小页扁平，大页再分层。
2. **与现有页面统一**：若同模块都是 `index.vue` 单文件，新页除非明显更复杂，否则不必单独搞一套「标准六件套」。
3. **类型与常量**：`WorkStatusFilter` 这类依赖 `typeof options` 时，优先让 **码表单独文件** 或 **types 只引用无环常量文件**，不要为了「一个 constants 入口」引入 `types ↔ constants` 循环。
4. **composables 语义**：静态码表、纯函数放在 `constants` 或 `utils`，不要塞进 `composables` 冒充 `useXxx`。
5. **重构节奏**：先写出可读版本，再按需抽离；不要一上来按文章铺满文件夹。

## 与项目其它技能的关系

- 新增路由与入口文件：仍优先遵循 [create-view](../create-view/SKILL.md)（`index.vue`、样式、路由注册）。
- 本技能补充的是：**复杂页在 `views` 内部的拆分粒度与目录命名**，二者可同时使用，以**可读、可维护、与周边一致**为准。

## 项目内示例

- 可参考 `src/views/storage/tape/`：含 `components/`、`composables/`、`constants/`（码表与表单选项分文件避免循环依赖）、根级 `types.ts`。这是**较完整**的示例，不是全项目最低标准。
