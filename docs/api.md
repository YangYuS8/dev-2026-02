# API 文档

## 基础信息

- Base URL: `https://api.yangyus8.top/dev-2026-02`
- 请求与响应格式：`application/json`

---

## 1. 获取任务列表

### 请求

```http
GET /tasks
```

### 响应示例

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "整理接口文档",
      "owner": "张三",
      "status": "doing",
      "createdAt": "2026-04-16T03:00:00.000Z"
    }
  ]
}
```

---

## 2. 新增任务

### 请求

```http
POST /tasks
Content-Type: application/json
```

### 请求体示例

```json
{
  "title": "完成首页样式",
  "owner": "李四",
  "status": "todo"
}
```

### 响应示例

```json
{
  "success": true,
  "message": "Task created successfully.",
  "data": {
    "id": 2,
    "title": "完成首页样式",
    "owner": "李四",
    "status": "todo",
    "createdAt": "2026-04-16T03:10:00.000Z"
  }
}
```

---

## 状态字段说明

- `todo`：待开始
- `doing`：进行中
- `done`：已完成

---

## 建议完成顺序

1. 先写获取任务列表
2. 再写渲染任务列表
3. 再写表单提交
4. 最后补筛选与错误提示
