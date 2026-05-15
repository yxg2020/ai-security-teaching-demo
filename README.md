# AI Security Teaching Demo

**AI 安全教学演示套件** — 面向 ICT 专业课程的交互式安全教学工具。

展示提示注入攻击（Prompt Injection）、编码绕过技术（Encoding Bypass）和多层防御方案（Multi-layer Defense），支持无 GPU 的演示模式和接入真实模型的实操模式。

## 功能

### ⚔️ 提示注入攻击演示
6 种攻击技术 × 6 个攻击场景，共 36 个教学组合：

| 攻击类型 | 攻击场景 |
|:---------|:---------|
| 直接指令注入 | 获取数据库密码 |
| 角色扮演绕过（DAN） | 获取入侵命令 |
| 上下文分隔攻击 | 生成带后门的代码 |
| 令牌走私 | 生成钓鱼邮件 |
| 前缀注入 | 绕过身份认证 |
| 假设场景绕过 | 数据外泄脚本 |

### 🔐 编码绕过技术
6 种编码绕过方式：Base64、Unicode 同形异码、字符反转、字符间隔插入、双层编码、摩斯电码包装。

### 🛡️ 多层防御方案
4 层防御体系 + 有无防御对比演示：
- 输入过滤与清洗
- 提示盾（Prompt Shield）
- 输出过滤与审核
- 多层防御体系

### 📚 课程关联
知识点自动映射到 4 门 ICT 课程：
- 网络与信息安全
- Linux 自动化运维
- 云计算部署与实施
- 软件测试与维护

## 快速开始

### 演示模式（无需 GPU，无需 API Key）

```bash
# 1. 安装依赖
pip install gradio

# 2. 启动
cd ai-security-demo
python3 app.py

# 3. 浏览器打开
# http://localhost:7861
```

### 真实模型模式（需要 GPU）

```bash
# 1. 安装 Ollama
curl -fsSL https://ollama.com/install.sh | sh
ollama pull qwen2.5:7b

# 2. 配置环境变量
export LLM_BACKEND=ollama
export OLLAMA_MODEL=qwen2.5:7b

# 3. 启动
python3 app.py
```

## 项目结构

```
ai-security-demo/
├── app.py              # Gradio Web 界面
├── security_core.py    # 核心攻击与防御逻辑
├── requirements.txt    # Python 依赖
├── .env.example        # 配置模板
└── README.md           # 本文件
```

## 配套工具

[AI Ops Assistant](https://github.com/your-repo/ai-ops-assistant) — AI 运维助手，自然语言生成 Shell 脚本 + 智能日志分析。

## 相关论文

> *AI 安全融入 ICT 专业课程的探索与实践——以提示注入攻防演示套件为例*
>
> 从注入目标、绕过方式、防御层次三个维度构建了面向 ICT 教学的攻击技术三维分类框架，建立了与 SQL 注入等传统攻击之间的知识映射关系。

## 环境要求

| 模式 | 硬件 | 软件 | 网络 |
|:----|:-----|:-----|:-----|
| 演示模式 | 任意电脑 | Python 3.9+, Gradio 5+ | 无 |
| Ollama 模式 | GPU, ≥8GB VRAM | Ollama, Qwen2.5-7B | 无 |
| OpenRouter 模式 | 任意电脑 | Python 3.9+, Gradio 5+ | 公网 |

## License

MIT
