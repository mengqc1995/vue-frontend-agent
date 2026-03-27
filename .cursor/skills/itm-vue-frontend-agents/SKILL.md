---
name: itm-vue-frontend-agents
description: 复用项目内 .agents 的前端规范与技能索引，指导 Vue 前端开发时按场景读取规则并执行实现步骤。用于用户提到 Vue 前端开发、页面/组件/API/store 新增改造、或要求遵循 .agents 规范时。
---

# ITM 前端规范迁移助手

## 适用场景

- 开发 Vue 前端页面、组件、接口、状态管理。
- 需要“按 `.agents` 规范实现”或“迁移 `.agents` 规则到当前任务”。
- 评审或改造现有代码，需要统一命名、结构、样式、测试与文档约束。

## 固定来源

- 优先使用当前项目下的 `.agents/rules` 与 `.agents/skills`。
- 若当前项目不存在 `.agents`，先向用户确认规范来源，再继续执行。

## 执行流程

复制并维护这个清单：

```markdown
Task Progress:
- [ ] Step 1: 确认任务类型与目标产物
- [ ] Step 2: 读取 rules/README.md 与 skills/README.md
- [ ] Step 3: 按场景读取必要规则文件
- [ ] Step 4: 按场景读取对应技能文件
- [ ] Step 5: 实施代码变更并自检命名/结构/约束
- [ ] Step 6: 输出结果与验证结论
```

### Step 1: 识别任务类型

将请求归类到以下一类或多类：

- 新增页面/视图
- 新增或拆分组件
- 新增 API
- 新增全局状态（Pinia）
- 样式/主题改造
- 通用重构与代码评审

### Step 2: 先读索引

优先读取：

- `rules/README.md`
- `skills/README.md`

目的是先建立“规则约束 + 操作步骤”的映射，不盲目编码。

### Step 3: 按需加载规则

最小必读：

- `08-通用约束.md`
- `02-编码规范.md`
- `03-项目结构.md`

按场景追加：

- 页面与路由：`06-路由规范.md`
- 组件：`04-组件规范.md`
- API：`05-API规范.md`
- 状态：`07-状态管理.md`
- 样式：`09-样式规范.md`
- 文档：`10-文档规范.md`
- 测试：`11-测试规范.md`

### Step 4: 按需加载技能

- 页面：`skills/create-view/SKILL.md`
- 复杂页面模块化：`skills/vue-page-module/SKILL.md`
- 组件：`skills/create-component/SKILL.md`
- API：`skills/create-api/SKILL.md`
- Store：`skills/create-store/SKILL.md`
- 主题/样式：`skills/theme-variables/SKILL.md`

### Step 5: 落地实现时的硬约束

- 注释与说明使用中文；标识符使用英文。
- 优先 TypeScript；若项目是 Vue SFC，遵循项目现状并保持一致。
- 命名严格执行：变量/函数 `camelCase`，组件 `PascalCase`，布尔值带 `is/has/can/...` 前缀。
- 目录遵循 `src/views`、`src/components`、`src/api`、`src/stores` 等既有结构，不新增非标准平行目录。
- 对于复杂页面按需拆分，避免教条式空目录。

### Step 6: 输出结果格式

输出时按以下结构：

```markdown
## 变更说明
- 任务类型：
- 读取规则：
- 读取技能：

## 实施内容
- 新增/修改文件：
- 关键决策：

## 规范对齐检查
- 命名规范：
- 目录结构：
- 通用约束：

## 验证
- 已执行：
- 未执行与原因：
```

## 额外资源

- 详细规则映射见 [reference.md](reference.md)
- 常见任务输入输出示例见 [examples.md](examples.md)
