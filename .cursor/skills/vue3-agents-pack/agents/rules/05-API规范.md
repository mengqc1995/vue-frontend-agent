---
alwaysApply: false
description: 接口请求封装、函数命名、错误处理。新增或修改接口时读取。
---

# API 规范

## 接口请求规范

- 请求统一使用 `utils/request` 封装。
- 接口按模块放在 `api/<module>/index.ts`（或单文件按模块划分）。
- 类型（Params/Body/Response）可放在同模块或 `types/` 下，保持与接口一致。

## 接口函数命名（NON-NEGOTIABLE）

| 操作 | 命名规则 | 示例 |
|------|----------|------|
| 获取列表 | getXxxList | getBannerList, getTapePool |
| 获取详情 | getXxxDetail | getBannerDetail |
| 创建 | createXxx | createTapePool |
| 更新 | updateXxx | updateTapePool |
| 删除 | deleteXxx | deleteTapePool |

禁止使用 fetch 前缀（如 fetchUserList）；统一使用 get/create/update/delete。

## 错误处理（NON-NEGOTIABLE）

- 接口错误由拦截器（如 request 封装内）统一处理。
- 业务代码只处理成功逻辑，禁止在业务中重复 message.error 等重复弹窗。
