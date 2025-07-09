# 【广发证券】MCP服务-财务分析

广发证券易淘金MCP Server 现已覆盖上市公司财务对比工具服务接口，提供沪深市场A股财务数据对比分析功能，通过对估值、盈利、现金流、偿债力、成长性的综合分析，直观比较两家上市公司的优势点和差异点，可为投资者提供多角度、长周期的参考数据，为投资决策给出客观数据支持。

## 什么是上市公司财务对比MCP服务？

广发证券易淘金MCP Server 现已覆盖上市公司财务对比工具服务接口，提供沪深市场A股财务数据对比分析功能，通过对估值、盈利、现金流、偿债力、成长性的综合分析，直观比较两家上市公司的优势点和差异点，可为投资者提供多角度、长周期的参考数据，为投资决策给出客观数据支持。

## 使用方式

### stdio

> ⚠️ 本方式已弃用，请使用 sse 方式接入。

```json
{
  "mcpServers": {
    "gf_quant": {
      "command": "npx",
      "args": ["-y" "@gfsecurities/mcp-base@1.0.3", "--appId=quant", "--sync=false"],
      "env": {
        "CONFIG_LOGGER": "silent",
        "GF_MCP_AUTH_KEY": "coze"
      }
    }
  }
}
```

### sse

```json
{
    "mcpServers": {
        "gf_quant": {
            "type": "sse",
            "url": "https://mcp-api.gf.com.cn/server/mcp/quant/sse",
            "headers": {
              "Authorization": "Bearer 2077f748-5b37-41ee-9d73-db5728639432"
            }
        }
    }
}
```

## 可用工具使用说明

### 1. 基本指标对比（单个或多个股票）

**工具名称**: `commonBasic`
**用途**: 获取单个或多个股票的基本指标，如市值与估值。

**示例**:

```json
{
  "stock_codes": ["SH600000", "SZ000776"]
}
```

### 2. 两个股票对比指标

**工具名称**: `commonIndicator`
**用途**: 对比两个股票的盈利、资本、现金等指标。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_codes": ["SH600000", "SZ000776"],
  "year": "2022"  // 使用最新年份
}
```

### 3. 股票行业信息

**工具名称**: `commonIndustryInfo`
**用途**: 获取股票的行业信息，包括行业代码、名称、龙头、相近等。

**示例**:

```json
{
  "stock_codes": ["SH600000", "SZ000776"]
}
```

### 4. 股票所在行业所有指标前二

**工具名称**: `commonIndustryTop2`
**用途**: 获取股票所在行业所有指标前二的股票。

**示例**:

```json
{
  "stock_code": "SZ000776"
}
```

### 5. 获取两个股票公共最近的报告期

**工具名称**: `commonReportType`
**用途**: 获取两个股票公共最近的报告期。

**示例**:

```json
{
  "stock_codes": ["SH600000", "SZ000776"]
}
```

### 6. 单个股票PB/PE走势图

**工具名称**: `commonTrend`
**用途**: 获取单个股票的PB/PE走势图。

**示例**:

```json
{
  "cycle": "1y",  // 1y表示1年周期
  "stock_code": "SZ000776"
}
```

### 7. 聚合查询

**工具名称**: `majorIndicatorAggregation`
**用途**: 聚合查询股票的多个财务指标。

**示例**:

```json
{
  "stock_code": "SZ000776"
}
```

### 8. 银行专项指标

**工具名称**: `majorIndicatorBank`
**用途**: 获取银行的专项财务指标。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 9. 现金流量表

**工具名称**: `majorIndicatorCashflow`
**用途**: 获取股票的现金流量表。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 10. 保险专项指标

**工具名称**: `majorIndicatorInsurance`
**用途**: 获取保险公司的专项财务指标。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 11. 资产负债表

**工具名称**: `majorIndicatorLiabilty`
**用途**: 获取股票的资产负债表。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 12. 主营业务构成饼图

**工具名称**: `majorIndicatorMainBusiness`
**用途**: 获取股票的主营业务构成饼图。

**示例**:

```json
{
  "stock_code": "SZ000776"
}
```

### 13. 利润表

**工具名称**: `majorIndicatorProfit`
**用途**: 获取股票的利润表。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 14. 证券专项指标

**工具名称**: `majorIndicatorSecurities`
**用途**: 获取证券公司的专项财务指标。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 15. 盈利能力分析

**工具名称**: `analyzeProfitAbility`
**用途**: 分析股票的盈利能力。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 16. 资本结构分析

**工具名称**: `analyzeCapitalStructure`
**用途**: 分析股票的资本结构。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```

### 17. 现金流量分析

**工具名称**: `analyzeCrashflow`
**用途**: 分析股票的现金流量。

**示例**:

```json
{
  "report_type": 12,  // 12表示年报，可以使用最新报告期
  "stock_code": "SZ000776"
}
```


## 常见问题解答

Q：使用广发证券MCP服务是否需要付费

A：该服务目前限时免费体验，未来广发证券将根据平台规范以及业务需求，进行必要适时的服务策略调整。

