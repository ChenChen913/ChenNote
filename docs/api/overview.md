# API 概述

## 接口规范

所有 API 遵循 RESTful 设计规范。

### 基础URL

```
https://api.example.com/v1
```

### 认证方式

所有接口需要在请求头中携带认证信息：

```http
Authorization: Bearer <your-token>
```

### 响应格式

```json
{
    "code": 0,
    "message": "success",
    "data": {}
}
```

### 错误码说明

| 错误码 | 说明 |
|--------|------|
| 0 | 成功 |
| 1001 | 参数错误 |
| 1002 | 认证失败 |
| 1003 | 权限不足 |
| 2001 | 资源不存在 |
| 5000 | 服务器内部错误 |
