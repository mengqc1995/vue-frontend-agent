---
name: create-view
description: 按项目规范新增页面视图并在路由中注册。新增或改版页面时使用。
---

# 新增页面视图

## 使用时机

需要新增一个页面（对应一条路由）时使用。配合规则：03-项目结构、06-路由规范、04-组件规范。

## 步骤概览

1. **在 views 下创建页面目录与入口**
   - 在 `src/views/` 下新建目录（命名与路由 path 对应，如 camelCase 的模块名）。
   - 创建 `index.vue` 作为页面入口；**`.vue` 文件中的样式块统一使用：**

```vue
<style lang="scss" scoped>
</style>
```

   - 如需独立样式文件，在同目录下建 `scss/index.scss` 或 `index.scss` 并在组件中引用。
   - 组件需符合 04-组件规范（BEM、无内联样式等见 09-样式规范）。

2. **在路由中注册（仅 ITM 系统）**
   - 在 `src/router/routes.ts` 的 `dynamicRoutesChildren` 数组中添加一条路由记录。
   - `path` 与 `name` 与项目现有风格一致；`component` 使用 `() => import('/@/views/xxx/index.vue')`。
   - 填写 `meta`（title、icon、roles、order 等），与菜单展示一致；参考同文件中已有路由的 meta 结构。

3. **确认菜单与权限**
   - 若项目为前端控制菜单，路由即菜单来源，确保 meta 正确即可。
   - 若为后端控制菜单，需与后端约定 path/name，保持一致。

## 产出

- `src/views/<module>/index.vue`（及可选样式文件）。
- `router/routes/` 对应文件中新增一条路由记录。
