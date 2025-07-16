# 【广发证券】MCP服务-龙虎榜

广发证券易淘金MCP Server 现已覆盖沪深股市龙虎榜分析工具服务接口，提供沪深两市A股龙虎榜数据分析功能，包括上榜统计、营业部排名、个股上榜历史、资金流向、买卖盘口等五大维度的龙虎榜报告，支持多维度时间区间查询（近1月/3月/6月/12月）。用户可通过该服务快速获取市场热点、机构活跃度及主力资金动向，为投资决策提供专业数据支持。

## 什么是沪深股市龙虎榜MCP服务？

广发证券易淘金MCP Server 现已覆盖沪深股市龙虎榜分析工具服务接口，提供沪深两市A股龙虎榜数据分析功能，包括上榜统计、营业部排名、个股上榜历史、资金流向、买卖盘口等五大维度的龙虎榜报告，支持多维度时间区间查询（近1月/3月/6月/12月）。用户可通过该服务快速获取市场热点、机构活跃度及主力资金动向，为投资决策提供专业数据支持。

## 使用方式

### stdio

> ⚠️ 本方式已弃用，请使用 sse 方式接入。
<details>

```json
{
  "mcpServers": {
    "gf_lhb": {
      "command": "npx",
      "args": ["-y" "@gfsecurities/mcp-base@1.0.3", "--appId=lhb", "--sync=false"],
      "env": {
        "CONFIG_LOGGER": "silent",
        "GF_MCP_AUTH_KEY": "<auth_key>"
      }
    }
  }
}
```

</details>

### sse

```json
{
    "mcpServers": {
        "gf_lhb": {
            "type": "sse",
            "url": "https://mcp-api.gf.com.cn/server/mcp/lhb/sse",
            "headers": {
              "Authorization": "Bearer 2077f748-5b37-41ee-9d73-db5728639432"
            }
        }
    }
}
```

## 相关工具使用示例

### 1. 获取指定日期和市场上榜的个股列表

**工具名称**: `lhb_aborttrade_market_date_get`
**用途**: 获取指定日期和市场上榜的个股列表。

**示例**:

```json
{
  "date": 20250528,
  "market": "sh"
}
```

### 2. 获取指定日期和个股上榜的明细

**工具名称**: `lhb_aborttrade_market_code_date_get`
**用途**: 获取指定日期和个股上榜的明细。

**示例**:

```json
{
  "code": "600000",
  "date": 20230906,
  "market": "sh"
}
```

### 3. 获取指定个股上榜列表

**工具名称**: `lhb_aborttrade_stock_market_code_get`
**用途**: 获取指定个股上榜列表。

**示例**:

```json
{
  "code": "600000",
  "market": "sh"
}
```

### 4. 获取指定时间区间内上榜个股排行列表

**工具名称**: `lhb_stat_stock_months_get`
**用途**: 获取指定时间区间内上榜个股排行列表。

**示例**:

```json
{
  "months": "m3",
  "page": 1,
  "pageSize": 10
}
```

### 5. 获取指定个股在指定时间区间内的统计数据

**工具名称**: `lhb_stat_stock_market_code_months_get`
**用途**: 获取指定个股在指定时间区间内的统计数据。

**示例**:

```json
{
  "code": "600000",
  "market": "sh",
  "months": "m6"
}
```

### 6. 获取指定营业部在指定时间区间内的统计数据

**工具名称**: `lhb_stat_dept_id_months_get`
**用途**: 获取指定营业部在指定时间区间内的统计数据。

**示例**:

```json
{
  "id": "T000244751",
  "months": "m12"
}
```

### 7. 获取龙虎榜、评级概括

**工具名称**: `lhb_outline_plate_get`
**用途**: 获取龙虎榜、评级概括。

**示例**:

```json
{
  "plate": "lhb"
}
```

### 8. 获取龙虎榜日历

**工具名称**: `lhb_calendar_market_month_get`
**用途**: 获取龙虎榜日历。

**示例**:

```json
{
  "market": "sh",
  "month": 202505
}
```

### 9. 获取个股列表上龙虎榜情况

**工具名称**: `lhb_aborttrade_batchstock_post`
**用途**: 获取个股列表上龙虎榜情况。

**示例**:

```json
{
  "date": 20250526,
  "months": "m1",
  "page": 1,
  "pageSize": 10
}
```


## 常见问题解答

Q：使用广发证券MCP服务是否需要付费

A：该服务目前限时免费体验，未来广发证券将根据平台规范以及业务需求，进行必要适时的服务策略调整。

