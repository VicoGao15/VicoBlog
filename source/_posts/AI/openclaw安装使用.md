---
title: 安装流程总结（Windows
date: 2026-3-10 11:00:00
category:
  - AI
banner: /assets/cover/doc.jpg
---

# OpenClaw 安装流程总结（Windows + WSL2 + Ollama 版）

目标：本地运行 OpenClaw，使用 Ollama（qwen3:8b）作为免费 LLM
openclaw文档：docs.openclaw.ai

## 1. 准备阶段

1. 启用 WSL2
   - PowerShell (管理员) 执行：`wsl --install`
   - 重启电脑
   - 打开 Ubuntu，设置用户名/密码

2. 安装 Ollama（Windows 本机）
   - 下载：https://ollama.com/download → Windows .exe
   - 安装后自动启动（托盘图标）
   - 测试：`ollama run qwen3:8b`（下载模型 + 聊天测试）

## 2. 安装 OpenClaw（在 WSL Ubuntu 终端）

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon   # 完成向导（可 skip search/channel）
```

## 3. 关键节点 & 配置顺序

1.启动 Gateway（最重要一步，常卡在这里）
```Bash
openclaw gateway install
openclaw gateway start
# 或启用 systemd 后：
systemctl --user start openclaw-gateway.service
```
- 验证：openclaw status → Gateway 应显示 reachable / running
- 浏览器打开：http://127.0.0.1:18789/

2.Dashboard 授权 token
- 页面显示 unauthorized → token missing
- 命令获取：openclaw gateway token
- 复制 token → dashboard 设置里粘贴 → 连接成功

3.配置 Ollama 模型（本地免费核心）
- 确认 Ollama 运行在 Windows
- WSL 测试连通（见坑 1）
- 配置命令：
```Bash
openclaw config set agents.main.provider ollama
openclaw config set agents.main.baseUrl "http://你的Windows_IP:11434/v1"   # 或 127.0.0.1 如果用 portproxy
openclaw config set agents.main.apiKey "ollama"
openclaw config set agents.main.model "qwen3:8b"
openclaw gateway restart
```

## 快速验证成功

- openclaw status → Gateway reachable
- Dashboard 打开正常，聊天区能回复
- 发送消息不报错，响应来自 qwen3:8b

## 建议保存的命令清单
```Bash
# 重启一切
wsl --shutdown
# Ubuntu 内
openclaw gateway restart
openclaw status
curl http://192.168.1.100:11434/v1/models   # 测试 Ollama
```
完成以上步骤后，OpenClaw + 本地 qwen3:8b 即可正常使用。
如需重新安装，直接按 1→2→3 顺序执行即可。