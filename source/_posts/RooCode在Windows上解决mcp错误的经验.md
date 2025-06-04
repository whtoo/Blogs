# RooCode在Windows上解决mcp错误的经验

## 问题现象
Context7 MCP服务器启动失败，原配置：
```json
{
  "command": "npx",
  "args": ["-y", "@upstash/context7-mcp"]
}
```

## 解决方案
1. **补全路径**：
   - Node执行文件：`C:\\Program Files\\nodejs\\node.exe`
   - 模块入口点：`C:\\Users\\Administrator\\AppData\\Roaming\\npm\\node_modules\\@upstash\\context7-mcp\\dist\\index.js`

2. **路径转义**：
   - Windows路径需转为双反斜杠`\\`
   - 保留环境变量`DEFAULT_MINIMUM_TOKENS`

## 最终配置
```json
{
  "command": "C:\\\\Program Files\\\\nodejs\\\\node.exe",
  "args": ["C:\\\\Users\\\\Administrator\\\\AppData\\\\Roaming\\\\npm\\\\node_modules\\\\@upstash\\\\context7-mcp\\\\dist\\\\index.js"],
  "env": {"DEFAULT_MINIMUM_TOKENS":"6000"}
}
```

## 验证命令
```shell
node "C:\...\index.js" --version