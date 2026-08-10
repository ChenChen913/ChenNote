# 接口列表

## 用户模块

### 获取用户信息

`GET /v1/users/{id}`

**路径参数**

| 参数 | 类型 | 说明 |
|------|------|------|
| id | string | 用户ID |

**响应示例**

```json
{
    "code": 0,
    "data": {
        "id": "u_001",
        "name": "张三",
        "email": "zhangsan@example.com",
        "created_at": "2025-01-01T00:00:00Z"
    }
}
```

---

### 创建用户

`POST /v1/users`

**请求体**

```json
{
    "name": "张三",
    "email": "zhangsan@example.com",
    "password": "******"
}
```

---

## 文档模块

### 获取文档列表

`GET /v1/docs?page=1&size=20`

**查询参数**

| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| size | int | 20 | 每页数量 |

!!! tip "提示"
    查看 [API 概述](overview.md) 了解通用规范。
