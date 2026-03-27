---
name: create-store
description: 使用 Pinia 新增或维护全局状态 store。新增或重构状态时使用。
---

# 新增 Pinia Store

## 使用时机

需要新增或调整全局状态时使用。配合规则：07-状态管理。

## 步骤概览

1. **确定 store 文件位置**
   - 在 `src/stores/` 下新增或修改文件，按业务模块命名（如 `tape.ts`、`userInfo.ts`）。

2. **定义 store**
   - 使用 `defineStore` 定义；state、getters、actions 按 Pinia 约定编写。
   - 导出命名：`useXxxStore`（如 useTapeStore、useUserStore）。

3. **持久化（可选）**
   - 若需持久化，使用项目已有的 persist 方案（如 `persist: true` 或 pinia-plugin-persistedstate）。

## 产出

- `src/stores/<module>.ts` 中新增或更新 store 定义，并暴露 `useXxxStore`。
