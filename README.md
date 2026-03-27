# vue-frontend-agent

> 面向 Cursor 的 Vue3 前端规范 Skill 包。内置 rules + skills，可直接在任意 Vue3 项目复用。

## 仓库结构

```
vue-frontend-agent/
├── README.md
└── .cursor/
    └── skills/
        └── vue3-agents-pack/
            ├── SKILL.md
            └── agents/
                ├── rules/
                └── skills/
```

## 快速使用

### 1) 项目级启用（推荐）

将本仓库的 `.cursor/skills/vue3-agents-pack` 复制到你的 Vue3 项目根目录：

```bash
mkdir -p /your-vue3-project/.cursor/skills
cp -r .cursor/skills/vue3-agents-pack /your-vue3-project/.cursor/skills/
```

然后用 Cursor 打开该项目即可生效。

### 2) 全局启用（所有项目可用）

```bash
mkdir -p ~/.cursor/skills
cp -r .cursor/skills/vue3-agents-pack ~/.cursor/skills/
```

安装后，在任意 Vue3 项目中都可使用该技能包。

## Skill 能力

- 新增页面/视图：按路由、结构和组件规范生成。
- 复杂页面拆分：按模块化方式组织 `components/composables/types`。
- 新增 API：按接口封装规范生成请求层。
- 新增 Pinia Store：按状态管理规范组织全局状态。
- 样式主题改造：按样式规范做变量化和结构化调整。

## 触发示例

- “按规范新增一个 Vue3 列表页，包含筛选和详情抽屉”
- “帮我按规范封装 user/list 接口并接入 Pinia”
- “把这个页面改成主题变量，避免硬编码颜色”

## 说明

- 本仓库已移除 `itm-vue-frontend-agents` 旧目录。
- 当前统一使用 `vue3-agents-pack` 作为唯一入口。
