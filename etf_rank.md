# 【广发证券】MCP服务-热门ETF榜单

## 什么是热门ETF榜单MCP服务？

热门ETF榜单服务接口，提供沪深市场ETF的热点排行，支持涨跌榜、资金榜、特色榜三大类特色排行数据，从13个维度全面统计当前市场热点。看排行找机会，掘金热点ETF。通过对估值、盈利、现金流、偿债力、成长性的综合分析，直观比较两家上市公司的优势点和差异点，可为投资者提供多角度、长周期的参考数据，为投资决策给出客观数据支持。

## 使用方式

### streamable-http

```json
{
    "mcpServers": {
        "gf_etfrank": {
            "type": "streamable-http",
            "url": "https://mcp-api.gf.com.cn/server/mcp/etf_rank/mcp",
            "headers": {
              "Authorization": "Bearer 2077f748-5b37-41ee-9d73-db5728639432"
            }
        }
    }
}
```

### sse

```json
{
    "mcpServers": {
        "gf_etfrank": {
            "type": "sse",
            "url": "https://mcp-api.gf.com.cn/server/mcp/etf_rank/sse",
            "headers": {
              "Authorization": "Bearer 2077f748-5b37-41ee-9d73-db5728639432"
            }
        }
    }
}
```

## 可用工具

| 工具名称                           | 用途                     |
|------------------------------------|--------------------------|
| finance-api_product_etf_rank_get   | 获取ETF各类榜单数据      |

---

## 可用参数说明

| 参数名              | 类型    | 必填 | 描述                                         | 示例   |
|---------------------|---------|------|----------------------------------------------|--------|
| type                | string  | 是   | 榜单类型（见下表）                           | "1"   |
| size                | integer | 否   | 条数，默认10                                 | 10     |
| page                | integer | 否   | 页数，默认0，从0开始                         | 0      |
| sameIndexFilter     | integer | 否   | 相同跟踪指数ETF仅显示1只，1：打开，0：关闭   | 1      |
| continueRiseLimit   | integer | 否   | 过滤连涨连跌天数，默认为0不过滤               | 3      |

**type 榜单类型说明：**
1、涨幅榜 2、跌幅榜 3、换手榜 4、主力资金榜 5、搜索榜 6、关注榜 7、5日涨幅榜 8、5日跌幅榜 9、连涨榜 10、连跌榜 11、5日主力资金榜 12、净申购榜 13、溢价率榜

---

## 相关工具使用示例

### 1. 获取ETF涨幅榜（默认参数）

```json
{
  "type": "1"
}
```

### 2. 获取ETF跌幅榜，返回20条，显示全部同指数ETF

```json
{
  "type": "2",
  "size": 20,
  "sameIndexFilter": 0
}
```

### 3. 获取ETF换手榜，第2页

```json
{
  "type": "3",
  "page": 1
}
```

### 4. 获取5日涨幅榜，过滤连涨3天的ETF

```json
{
  "type": "7",
  "continueRiseLimit": 3
}
```

### 5. 获取主力资金榜，返回5条

```json
{
  "type": "4",
  "size": 5
}
```

---

## 常见问题解答

Q：使用广发证券MCP服务是否需要付费

A：该服务目前限时免费体验，未来广发证券将根据平台规范以及业务需求，进行必要适时的服务策略调整。

