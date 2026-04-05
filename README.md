# SOAR-CLI

**soar-cli** 是一个专为人类操作和 AI Agent 自动化集成设计的轻量级命令行工具，旨在便捷地对接和调用编排自动化产品 OctoMation / HoneyGuide SOAR，执行安全剧本（Playbook）。

本开源项目由 **[上海雾帜智能科技有限公司 (flagify.com)](https://flagify.com/)** 提供技术支持。

### 兄弟项目系列
- **soar-cli** (本项目): [https://github.com/flagify-com/soar-cli](https://github.com/flagify-com/soar-cli)
- **soar-mcp**: [https://github.com/flagify-com/soar-mcp](https://github.com/flagify-com/soar-mcp)
- **OctoMation 核心引擎**: [https://github.com/flagify-com/OctoMation](https://github.com/flagify-com/OctoMation)

---

## 📦 安装与初始化

```bash
# 获取代码库
cd /opt/code/chris/SuperBody/dev/soar_cli

# (推荐) 创建并激活独立的虚拟环境
python3 -m venv venv
source venv/bin/activate

# 以可编辑模式进行本地安装
pip install -e .
```

## ⚙️ 配置文件配置
将源码包中的 `.env.example` 复制为 `.env` 并填入你的后端地址与认证 Token。

```bash
cp .env.example .env
```

## 👩‍💻 使用方法 (人类模式)
人类模式下，CLI 终端会自动渲染彩色的 ASCII 数据表，方便直观查看数据。

```bash
soar-cli playbook --help
soar-cli playbook list
soar-cli playbook search "暴力破解"

# 执行某个设定的剧本并赋予配置参数
soar-cli playbook execute 123 --params '{"ip": "1.1.1.1"}'

# 检查执行进度或状态
soar-cli playbook status xyz-123

# 拉取执行结果
soar-cli playbook result xyz-123
```

## 🤖 使用方法 (Agent/大模型 严格 JSON 模式)
专为 LLMs / AutoGPT / 各种脚手架及调度任务定制。只需在全球任意命令前加上 `--json` (或 `-j`)。
所有终端富文本和交互输出会被立即屏蔽，仅输出严格的、可解析的 JSON 对象。

```bash
soar-cli --json playbook list
soar-cli --json playbook execute 123 --params '{"ip":"1.1.1.1"}'
soar-cli --json playbook result xyz-123
```
