# 【广发证券】MCP服务-沪深指数估值分析

## 什么是沪深指数估值分析MCP服务？

沪深指数估值分析工具接口，通过该工具来判断指数的投资潜力，遵循“低买高卖”的原则，提示投资者可以在估值不高时考虑入场，静静等待上涨机会，并在估值较高时做出提醒。同时，该功能还进一步把指数和相关热门ETF进行配对关联，帮助投资者快速查询投资标的，提高投资决策效率。

## 使用方式

### streamable-http

```json
{
    "mcpServers": {
        "gf_windmill": {
            "type": "streamable-http",
            "url": "https://mcp-api.gf.com.cn/server/mcp/windmill/mcp",
            "headers": {
              "Authorization": "Bearer 2077f748-5b37-41ee-9d73-db5728639432"
            }
        }
    }
}
```

### streamable-http

```json
{
    "mcpServers": {
        "gf_windmill": {
            "type": "streamable-http",
            "url": "https://mcp-api.gf.com.cn/server/mcp/windmill/mcp",
            "headers": {
              "Authorization": "Bearer <YOUR_TOKEN>"
            }
        }
    }
}
```

## 可用工具

| 工具名称                                 | 用途                       |
|------------------------------------------|----------------------------|
| valuation_windmill_get                   | 获取指数估值&顺风车榜单数据 |

---

## 可用参数说明

| 参数名   | 类型    | 必填 | 描述         | 示例 |
|----------|---------|------|--------------|------|
| page     | integer | 否   | 页码，默认0  | 0    |
| perPage  | integer | 否   | 每页数量，默认10 | 10   |

---

## 相关工具使用示例

### 1. 获取第一页（默认）
```json
{}
```

### 2. 获取第2页，每页5条
```json
{
  "page": 1,
  "perPage": 5
}
```

---

## 常见问题解答

Q：使用广发证券MCP服务是否需要付费

A：该服务目前限时免费体验，未来广发证券将根据平台规范以及业务需求，进行必要适时的服务策略调整。 