# 使用示例

## 示例 1：新增 Vue 列表页

**输入：**
“新增一个设备列表页，含筛选、表格、详情抽屉，并配置路由。”

**执行：**

1. 读取 `rules/README.md`、`skills/README.md`。
2. 读取规则：`03-项目结构.md`、`06-路由规范.md`、`04-组件规范.md`、`08-通用约束.md`。
3. 读取技能：`skills/create-view/SKILL.md`；若页面较复杂再读取 `skills/vue-page-module/SKILL.md`。
4. 实施并检查命名/目录/可观测性。

**输出示例：**

```markdown
## 变更说明
- 任务类型：新增页面/路由
- 读取规则：03、04、06、08
- 读取技能：create-view、vue-page-module

## 实施内容
- 新增 views/deviceList/index.vue
- 新增 views/deviceList/components/FilterBar.vue
- 新增 views/deviceList/components/DetailDrawer.vue
- 更新 router/routes/common.ts

## 规范对齐检查
- 命名规范：组件 PascalCase，事件/处理函数 onXxx/handleXxx
- 目录结构：仅在 views 下扩展页面内目录，无非标准目录
- 通用约束：异常请求有兜底提示

## 验证
- 已执行：类型检查、页面手动联调
- 未执行：自动化测试（当前仓库无对应脚本）
```

## 示例 2：新增 API + Store

**输入：**
“给设备模块新增分页查询接口，并在 Pinia 中管理列表状态。”

**执行：**

1. 规则：`05-API规范.md`、`07-状态管理.md`、`02-编码规范.md`、`08-通用约束.md`。
2. 技能：`skills/create-api/SKILL.md`、`skills/create-store/SKILL.md`。
3. 代码完成后，检查函数动词命名、布尔前缀、错误兜底。

## 示例 3：样式主题改造

**输入：**
“把页面色板改成主题变量，避免硬编码颜色值。”

**执行：**

1. 规则：`09-样式规范.md`、`08-通用约束.md`。
2. 技能：`skills/theme-variables/SKILL.md`。
3. 输出需标注替换点与回归验证结果。
