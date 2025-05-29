# 【广发证券】MCP服务-龙虎榜

广发证券易淘金MCP Server 现已覆盖沪深股市龙虎榜分析工具服务接口，提供沪深两市A股龙虎榜数据分析功能，包括上榜统计、营业部排名、个股上榜历史、资金流向、买卖盘口等五大维度的龙虎榜报告，支持多维度时间区间查询（近1月/3月/6月/12月）。用户可通过该服务快速获取市场热点、机构活跃度及主力资金动向，为投资决策提供专业数据支持。

## 什么是沪深股市龙虎榜MCP服务？

广发证券易淘金MCP Server 现已覆盖沪深股市龙虎榜分析工具服务接口，提供沪深两市A股龙虎榜数据分析功能，包括上榜统计、营业部排名、个股上榜历史、资金流向、买卖盘口等五大维度的龙虎榜报告，支持多维度时间区间查询（近1月/3月/6月/12月）。用户可通过该服务快速获取市场热点、机构活跃度及主力资金动向，为投资决策提供专业数据支持。

## 使用方式

### stdio

```json
{
  "mcpServers": {
    "gf_lhb": {
      "command": "npx",
      "args": ["-y" "@gfsecurities/mcp-base@1.0.3", "--appId=lhb", "--sync=false"],
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
        "gl_lhb": {
            "type": "sse",
            "url": "https://cloud1-3gr3bpci71d1de86.api.tcloudbasegateway.com/v1/cloudrun/gf-lhb/messages",
            "headers": {
              "Authorization": "Bearer eyJhbGciOiJSUzI1NiIsImtpZCI6IjlkMWRjMzFlLWI0ZDAtNDQ4Yi1hNzZmLWIwY2M2M2Q4MTQ5OCJ9.eyJhdWQiOiJjbG91ZDEtM2dyM2JwY2k3MWQxZGU4NiIsImV4cCI6MjUzNDAyMzAwNzk5LCJpYXQiOjE3NDc4ODc3ODcsImF0X2hhc2giOiJkbFBtWFRiRUVmQzg4VkpVQUdrb2xRIiwicHJvamVjdF9pZCI6ImNsb3VkMS0zZ3IzYnBjaTcxZDFkZTg2IiwibWV0YSI6eyJwbGF0Zm9ybSI6IkFwaUtleSJ9LCJ1c2VyX3R5cGUiOiIifQ.ZL3o2YWWxu2SozaAam35vyKOYEUqPgGfOzNAa2Ix3aW1BGfTbzh4gJHLuaAaqpRDTHdBamxw64RfYm6vGHXQ6r1AItI379ACrWs0Sxg6v-S1AtP6EnLtE9WmdJqS3xCMUvn1jQQwkBpoKxgiYalxb_koy66F0vMQLpAX3CLiKqWYX4hjMTRakC3n9PmIviA_fW5G8iOCRrG9Kjs8L7xQvFA52W91lhqOrUL_paFT7YEnLV4w5zmQz111e-ucAu4UfciVLmCWOqboeyht1Leh_AdVJ84Mlny4cbRi-K7nCvfuMq9ID2Wv1fWn0KFkhagnHfa9HRtCfJt-gxp_sVoWgA"
            }
        }
    }
}
```

## 常见问题解答

Q：使用广发证券MCP服务是否需要付费

A：该服务目前限时免费体验，未来广发证券将根据平台规范以及业务需求，进行必要适时的服务策略调整。

