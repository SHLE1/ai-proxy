# AI Proxy

这是一个简单的 AI 服务代理。

## 赞助商

本项目由 [ChatWise](https://chatwise.app) 赞助，ChatWise 是一款支持任何 LLM 的极速 AI 聊天机器人。

## 使用方法

将您的 API 域名替换为部署在您服务器上的代理域名。例如：

- Gemini：
  - 原地址：`https://generativelanguage.googleapis.com/v1beta`
  - 代理地址：`https://your-proxy/generativelanguage/v1beta`
- OpenAI：
  - 原地址：`https://api.openai.com/v1`
  - 代理地址：`https://your-proxy/openai/v1`
- Anthropic：
  - 原地址：`https://api.anthropic.com/v1`
  - 代理地址：`https://your-proxy/anthropic/v1`
- Groq：
  - 原地址：`https://api.groq.com/openai/v1`
  - 代理地址：`https://your-proxy/groq/openai/v1`
- Perplexity：
  - 原地址：`https://api.perplexity.ai`
  - 代理地址：`https://your-proxy/pplx`
- Mistral：
  - 原地址：`https://api.mistral.ai`
  - 代理地址：`https://your-proxy/mistral`
- OpenRouter：
  - 原地址：`https://openrouter.ai/api`
  - 代理地址：`https://your-proxy/openrouter`
- xAI：
  - 原地址：`https://api.xai.ai`
  - 代理地址：`https://your-proxy/xai`
- Cerebras：
  - 原地址：`https://api.cerebras.ai`
  - 代理地址：`https://your-proxy/cerebras`

## ChatWise 托管服务

使用我们托管的 API，例如 OpenAI：`https://ai-proxy.chatwise.app/openai/v1`

## 部署

### Docker 安装

#### 方式一：使用 Docker Hub 镜像

```bash
# 拉取镜像
docker pull hypered1/ai-proxy:latest

# 运行容器
docker run -d \
  --name ai-proxy \
  -p 3000:3000 \
  --restart unless-stopped \
  hypered1/ai-proxy:latest
```

#### 方式二：从源码构建

```bash
# 克隆仓库
git clone https://github.com/hypered/ai-proxy.git
cd ai-proxy

# 构建镜像
docker build -t ai-proxy .

# 运行容器
docker run -d \
  --name ai-proxy \
  -p 3000:3000 \
  --restart unless-stopped \
  ai-proxy
```

#### Docker Compose

创建 `docker-compose.yml` 文件：

```yaml
version: '3.8'

services:
  ai-proxy:
    image: hypered1/ai-proxy:latest
    # 或使用本地构建：build: .
    container_name: ai-proxy
    ports:
      - "3000:3000"
    restart: unless-stopped
    environment:
      - NODE_ENV=production
```

然后运行：

```bash
docker-compose up -d
```

### 配置说明

- 默认端口：`3000`
- 可通过环境变量 `PORT` 自定义端口

## 许可证

MIT.
