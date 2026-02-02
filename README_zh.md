# Ollama 模型导出/导入脚本
这些脚本将 Ollama 模型文件从本地主机导出到 tar 包，或将其传输到另一台主机，主要用于离线部署场景。

## 要求
- 主机上需要安装 `jq` 命令行工具。

## 安装
将脚本复制到任何目录即可，或运行系统范围安装命令：
```bash
install -m 555 ollama-export ollama-import /usr/bin
```

# 使用方法
## 将模型导出为 tar 包
```bash
ollama-export llama3.3:latest > llama3.3:latest.tar
```

## 导出并压缩模型为 gzip 格式的 tar 包
```bash
ollama-export llama3.3:latest | gzip -c > llama3.3:latest.tar.gz
```

## 导入本地 tar 包/gzip 格式 tar 包
```bash
ollama-import llama3.3:latest.tar.gz
```

## 通过 SSH 传输并导入模型到远程主机
```bash
ollama-export llama3.3:latest | ssh some_server ollama-import
```

# 注意事项
- 已在 CentOS 8 和 Ubuntu 20.04 上使用 Ollama 0.12.3 进行测试