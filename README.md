# AntV文档协议服务器 Extract Antv Topic

为AI开发和QA设计的模型上下文协议服务器，提供AntV文档上下文和代码示例。
A model context protocol server designed for AI development and QA, providing AntV document context and code examples.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| extract_antv_topic | AntV Intelligent Assistant Preprocessing Tool - Specifically designed to handle any user queries related to AntV visualization libraries.   This tool is the first step in processing AntV technology stack issues, responsible for intelligently identifying, parsing, and structuring user visualization requirements.  **MANDATORY: Must be called for ANY new AntV-related queries, including simple questions. Always precedes query_antv_document tool.**  When to use this tool: - **AntV-related queries**: Questions about g2/g6/l7/x6/f2/s2/g/ava/adc libraries. - **Visualization tasks**: Creating charts, graphs, maps, or other visualizations. - **Problem solving**: Debugging errors, performance issues, or compatibility problems. - **Learning & implementation**: Understanding concepts or requesting code examples.  Key features: - **Smart Library Detection**: Scans installed AntV libraries and recommends the best fit based on query and project dependencies. - **Topic & Intent Extraction**: Intelligently extracts technical topics and determines user intent (implement/solve). - **Task Complexity Handling**: Detects complex tasks and decomposes them into manageable subtasks. - **Seamless Integration**: Prepares structured data for the query_antv_document tool to provide precise solutions. |
| query_antv_document | AntV Context Retrieval Assistant - Fetches relevant documentation, code examples, and best practices from official AntV resources. Supports g2, g6, l7, x6, f2, s2, g, ava, adc libraries, and handles subtasks iterative queries.  **MANDATORY: Must be called for ANY AntV-related query (g2, g6, l7, x6, f2, s2, g, ava, adc), regardless of task complexity. No exceptions for simple tasks.**  When to use this tool: - **Implementation & Optimization**: To implement new features, modify styles, refactor code, or optimize performance in AntV solutions. - **Debugging & Problem Solving**: For troubleshooting errors, unexpected behaviors, or technical challenges in AntV projects. - **Learning & Best Practices**: To explore official documentation, code examples, design patterns, or advanced features. - **Complex Task Handling**: For multi-step tasks requiring subtask decomposition (e.g., "Build a dashboard with interactive charts"). - **Simple modifications**: Even basic changes like "Change the chart's color" or "Update legend position" in AntV context. |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659406851](https://mcp.xiaobenyang.com/inspector/1777316659406851)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659406851](https://mcp.xiaobenyang.com/inspector/1777316659406851)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "AntV文档协议服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659406851/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "AntV文档协议服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659406851/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "AntV文档协议服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659406851",
          },
          "transport": "stdio"
        }
      }
}

```
