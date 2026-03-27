---
name: create-component
description: 按项目规范创建或拆分 Vue 组件。新增或重构组件时使用。
---

# 创建或拆分组件

## 使用时机

需要新增通用组件或页面内组件时使用。配合规则：04-组件规范、09-样式规范。

## 步骤概览

1. **确定放置位置**
   - 通用（跨页面）：`src/components/<ComponentName>/`。
   - 仅单页使用：`views/<page>/components/` 或同页面目录下。
   - 目录与文件命名：目录 camelCase 或与组件名一致；单文件组件可用 `index.vue`。

2. **创建组件文件**
   - 创建 `index.vue`（或 `ComponentName.vue`）；样式使用 scoped，可为同目录下 `index.scss` 或 `scss/index.scss`。
   - Props 定义清晰接口；类名遵循 BEM，禁止内联样式（见 09-样式规范）。

3. **控制复杂度**
   - 单文件建议不超过 400 行；超过时拆分子组件或 composables。

## 产出

- `components/<name>/index.vue`（及可选样式文件），或 `views/<page>/components/<Name>.vue`。
