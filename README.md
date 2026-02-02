[中文](README_zh.md)

# Ollama Model Export/Import Scripts
These scripts export Ollama model files from a local host to a tarball, or transfer them to another host, primarily for offline deployment use cases.

## Requirements
- The `jq` command-line tool is required on the host.

## Installation
Copy the scripts to any preferred directory, or run the system-wide installation command:
```bash
install -m 555 ollama-export ollama-import /usr/bin
```

# Usage
## Export model to a tarball
```bash
ollama-export llama3.3:latest > llama3.3:latest.tar
```
## Export and compress model to a gzipped tarball
```bash
ollama-export llama3.3:latest | gzip -c > llama3.3:latest.tar.gz
```

## Import a local tarball/gzipped tarball
```bash
ollama-import llama3.3:latest.tar.gz
```

## Transfer and import model to a remote host via SSH
```bash
ollama-export llama3.3:latest | ssh some_server ollama-import
```

# Notes
- Tested with Ollama 0.12.3 on CentOS 8 and Ubuntu 20.04
