# soar-cli
支持AI Agent通过CLI方式调用编排自动化产品OctoMation / HoneyGuide SOAR，执行安全剧本Playbook

A command-line interface designed to easily interface with OctoMation / HoneyGuide.
Perfect for humans in terminal, and incredibly native for AI Agents with `--json`.

## Installation

```bash
cd /opt/soar_cli
# Optional but recommended: create a venv
python3 -m venv venv
source venv/bin/activate

# Install it locally
pip install -e .
```

## Configuration
Copy `.env.example` to `.env` and configure your keys.

```bash
cp .env.example .env
```

## Usage (Human Mode)
```bash
soar-cli playbook --help
soar-cli playbook list
soar-cli playbook search "封禁"
soar-cli playbook execute --id 123 --params '{"ip": "1.1.1.1"}'
soar-cli playbook status --exec-id xyz-123
```

## Usage (Agent Mode - Strict JSON)
For LLMs / AutoGPT / Scripts, append `--json`.

```bash
soar-cli --json playbook list
soar-cli --json playbook execute --id 123 --params '{"ip":"1.1.1.1"}'
```
