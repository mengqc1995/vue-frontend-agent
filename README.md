# vue-frontend-agent

> 面向 Cursor 的 Vue 前端开发规范 Skill，帮助 AI Agent 在开发 Vue 项目时自动遵循团队规范。

---

## 📁 仓库结构

```
vue-frontend-agent/
├── README.md
└── .cursor/
    └── skills/
        └── itm-vue-frontend-agents/
            ├── SKILL.md        # 主技能文件：执行流程与规范约束
            ├── reference.md    # 规则映射速查表
            └── examples.md     # 常见任务输入输出示例
```

---

## 🚀 如何在 Cursor 中启用这个 Skill

### 方式一：直接克隆本仓库（推荐）

```bash
git clone https://github.com/mengqc1995/vue-frontend-agent.git
cd vue-frontend-agent
```

用 Cursor 打开该目录，Skill 会自动生效（Cursor 会识别 `.cursor/skills/` 目录）。

---

### 方式二：复制到你的 Vue 项目中

将 `.cursor/` 目录整体复制到你的 Vue 项目根目录：

```bash
cp -r .cursor/skills/itm-vue-frontend-agents /your-vue-project/.cursor/skills/
```

然后用 Cursor 打开你的 Vue 项目，Skill 即可生效。

---

### 方式三：安装为全局 Skill（所有项目通用）

```bash
mkdir -p ~/.cursor/skills/itm-vue-frontend-agents
cp .cursor/skills/itm-vue-frontend-agents/* ~/.cursor/skills/itm-vue-frontend-agents/
```

安装后，在任意项目中打开 Cursor 均可使用该 Skill。

---

## 🧠 Skill 能做什么

| 场景 | Skill 行为 |
|------|-----------|
| 新增 Vue 页面/视图 | 自动读取路由规范、页面结构规范，按标准生成代码 |
| 新增组件 | 遵循组件命名、Props 定义、emit 规范 |
| 新增 API 接口 | 按 API 规范生成请求封装 |
| 新增 Pinia Store | 按状态管理规范生成 store 文件 |
| 代码评审/重构 | 对照通用约束与编码规范给出改进建议 |

---

## 📖 使用方式

在 Cursor 中，直接用自然语言描述任务即可，例如：

```
按 .agents 规范，新增一个用户列表页面
```

```
帮我创建一个 UserCard 组件，遵循项目规范
```

```
按规范封装 /api/user/list 接口
```

Skill 会自动：
1. 识别任务类型
2. 读取对应规则文件
3. 加载对应技能文件
4. 按规范实施代码变更
5. 输出规范对齐检查报告

---

## 📋 前置依赖

本 Skill 依赖项目内的 `.agents/` 目录（规则与技能索引）。  
若你的项目中没有 `.agents/`，Skill 会提示你确认规范来源后再继续执行。

---

## 🔗 相关资源

- [SKILL.md](.cursor/skills/itm-vue-frontend-agents/SKILL.md) — 完整执行流程
- [reference.md](.cursor/skills/itm-vue-frontend-agents/reference.md) — 规则映射速查
- [examples.md](.cursor/skills/itm-vue-frontend-agents/examples.md) — 示例输入输出
