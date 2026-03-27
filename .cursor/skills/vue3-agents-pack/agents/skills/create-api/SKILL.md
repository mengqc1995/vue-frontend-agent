---
name: create-api
description: 按项目规范新增或维护 HTTP 接口封装与类型。新增或调整 API 时使用。
---

# 新增接口

## 使用时机

需要新增或修改接口请求时使用。配合规则：05-API规范。

## 步骤概览

1. **确定接口归属模块**
   - 接口封装放在 `src/api/<module>/index.ts`（若模块已存在则在该文件中新增方法）。
   - 类型可放在同文件或 `src/types/` 下，与接口一一对应。

2. **命名与实现**
   - 列表：`getXxxList(params?)`；详情：`getXxxDetail(params?)`。
   - 创建/更新/删除：`createXxx(data)`、`updateXxx(data)`、`deleteXxx(params?)`。
   - 禁止使用 fetch 前缀。使用项目封装的 `request`（如 `utils/request`）发起请求。

3. **错误处理**
   - 业务代码只处理成功逻辑；错误由拦截器统一处理，不在业务中重复 message 等。

## 产出

- 在 `api/<module>/index.ts` 中新增或修改请求函数。
- 如需要，在类型文件中补充 Params/Body/Response 类型。
