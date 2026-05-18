# Getting Started

**Time required: 15 minutes**

## Step 1: Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Or download the VS Code extension: search "Claude Code" in the VS Code marketplace.

## Step 2: Get an Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Create an account
3. Go to API Keys → Create new key
4. Copy the key

**Cost estimate:** Building through the full 18-day course costs approximately $3-8 in API credits using Claude Sonnet. Less than a coffee.

## Step 3: Configure Claude Code

```bash
# Set your API key
export ANTHROPIC_API_KEY="sk-ant-..."

# Or add to ~/.zshenv for persistence
echo 'export ANTHROPIC_API_KEY="sk-ant-..."' >> ~/.zshenv
source ~/.zshenv
```

## Step 4: Install the OneMillion Agents

```bash
# Clone this repo
git clone https://github.com/your-org/onemillion-builder
cd onemillion-builder

# Copy agents to Claude's config
cp -r agents/* ~/.claude/agents/
cp -r skills/* ~/.claude/skills/
```

Verify agents are loaded:
```bash
claude
# Type: /agents
# You should see orchestrator, idea, spec, design, plan, build, test, guard, ship, sell listed
```

## Step 5: Install Prerequisites

The BUILD agent needs these tools. Install them now so you're ready on Day 11.

```bash
# Node.js 20+ (if not installed)
# Visit nodejs.org and install LTS version

# Python 3.11+
brew install python@3.13  # macOS
# Or visit python.org

# Verify
node -v   # should show v20+
python3 --version  # should show 3.11+
git --version  # should show git

# Global tools
npm install -g vercel @railway/cli

# Python tools
pip3 install reportlab
```

## Step 6: Create Your Project Directory

```bash
mkdir my-product && cd my-product
claude
```

You're ready. Start with [Day 1](./day-01/learn.md).
