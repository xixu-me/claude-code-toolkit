# Claude Code 工具包（Claude Code Toolkit, CCT）

***[English](README.md)***

[![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)](#命令语法)
[![macOS](https://img.shields.io/badge/macOS-000000?style=flat&logo=apple&logoColor=white)](#命令语法)
[![Windows](https://img.shields.io/badge/Windows-0078D6?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA4OCA4OCIgd2lkdGg9Ijg4IiBoZWlnaHQ9Ijg4Ij48cmVjdCB3aWR0aD0iNDIiIGhlaWdodD0iNDIiIGZpbGw9IiMwMGFkZWYiLz48cmVjdCB4PSI0NiIgd2lkdGg9IjQyIiBoZWlnaHQ9IjQyIiBmaWxsPSIjMDBhZGVmIi8+PHJlY3QgeT0iNDYiIHdpZHRoPSI0MiIgaGVpZ2h0PSI0MiIgZmlsbD0iIzAwYWRlZiIvPjxyZWN0IHg9IjQ2IiB5PSI0NiIgd2lkdGg9IjQyIiBoZWlnaHQ9IjQyIiBmaWxsPSIjMDBhZGVmIi8+PC9zdmc+&logoColor=white)](#命令语法)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

一个功能全面的跨平台工具包，用于管理 Claude Code 的安装、配置以及对多个 Anthropic 兼容 API 提供商的支持。该工具包简化了设置和切换不同 Anthropic 兼容 API 提供商的过程，包括官方 Anthropic API 和实现了 Anthropic API 规范的兼容第三方服务，例如 **月之暗面（Moonshot AI）最新的 Kimi 模型（`kimi-k2-0711-preview`）**。

## 🎬 为 Agent 工作流接入创意生成

如果 Claude Code 会话还需要生成视频、图片或音乐，可以试试 [Renoise](https://renoise.ai/plugin)：它通过 MCP 在对话中承接创意简报并完成生成迭代。安装与工作流说明见[官方插件仓库](https://github.com/ArcoCodes/renoise-plugins-official)。

## 🍬 Claude Code Sugar

寻求更广泛的模型兼容性？请查看 **[Claude Code Sugar](sugar/)** - 一个轻量级的本地代理工具，它允许 Claude Code 与任何兼容 OpenAI API 规范的服务进行交互，例如魔搭社区（ModelScope）平台。通过 Sugar，您可以将 `claude` 命令请求无缝对接到更广阔的 AI 模型生态系统，同时保持现有的工作流程不变。

> 📖 **关于链接优化**: 为提升用户访问体验，本文提供了通过 **[Xget](https://github.com/xixu-me/Xget)** 优化的 GitHub 链接选项。Xget 是基于 Cloudflare Workers 构建的开源服务，用于改善 GitHub、GitLab 和 Hugging Face 等开源平台的连接稳定性，提供智能缓存（30 分钟 TTL）、HTTP/3 支持、自动重试机制以及安全防护功能。用户可根据自身网络环境选择使用。

## ✨ 最新 Kimi 模型支持

🚀 **亮点**: 本工具包内置支持**月之暗面（Moonshot AI）最新的 Kimi 模型（`kimi-k2-0711-preview`）**，让您可以通过熟悉的 Claude Code 界面利用前沿的 AI 功能。

- **一键设置**: 快速配置月之暗面（Moonshot AI）及最新的 Kimi 模型。
- **无缝切换**: 在官方 Anthropic API 和 Kimi 模型之间轻松切换。
- **完全兼容**: 所有 Claude Code 功能均可与 Kimi 模型无缝协作。

## 功能特性

- **跨平台支持**: 适用于 Linux/macOS（Bash）和 Windows（PowerShell）。
- **多提供商支持**: 在 Anthropic、月之暗面（Moonshot AI，含最新 Kimi 模型）及自定义 Anthropic 兼容 API 提供商之间轻松切换。
- **自动化安装**: 处理 Node.js、npm 和 Claude Code 软件包的安装。
- **配置管理**: 持久化提供商配置，并安全存储 API 密钥。
- **环境变量管理**: 自动配置 Shell 环境，实现无缝的提供商切换。
- **交互式设置**: 在未提供参数时，通过用户友好的提示进行配置。

## 系统要求

- **Node.js** 18 或更高版本
- **npm**（Node Package Manager）
- **Bash**（适用于 Linux/macOS）或 **PowerShell**（适用于 Windows）
- 用于下载软件包的互联网连接

## API 密钥设置

在使用本工具包前，您需要从所选的提供商获取 API 密钥：

- **Anthropic API**: 从 [Anthropic Console](https://console.anthropic.com/) 获取您的 API 密钥。
- **月之暗面（Moonshot AI）**: 从 [Moonshot AI 开放平台](https://platform.moonshot.cn/console) 获取您的 API 密钥。
- **自定义提供商**: 从您偏好的 Anthropic 兼容服务获取 API 密钥。

## 使用方法

### 可用命令

| 命令 | 描述 |
|---------|-------------|
| `install [provider] [api_key] [options]` | 安装 Claude Code 并配置一个提供商 |
| `uninstall` | 完全移除 Claude Code 及所有配置 |
| `update` | 将 Claude Code 更新到最新版本 |
| `check` | 检查安装状态和当前提供商 |
| `add-provider <name> <url> <key>` | 添加一个新的 API 提供商配置 |
| `switch <provider>` | 切换到另一个已配置的提供商 |
| `list-providers` | 显示所有可用的提供商 |

### 命令语法

对于以下所有命令，请使用对应的模式：

**Linux/macOS（Bash）：**

```bash
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s [command] [arguments]
```

**Windows（PowerShell）：**

```powershell
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 [command] [arguments]
```

### 快速入门示例

#### 1. 基本安装 (交互式设置)

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s install

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 install
```

#### 2. 使用 Anthropic（官方 API）安装

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s install Anthropic 你的API密钥

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 install Anthropic 你的API密钥
```

#### 3. 使用月之暗面（最新 Kimi 模型）安装

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s install "Moonshot AI" 你的API密钥

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 install "Moonshot AI" 你的API密钥
```

#### 4. 使用自定义提供商安装

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s install "自定义提供商名称" 你的API密钥 --base-url https://api.example.com/v1/

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 install "自定义提供商名称" 你的API密钥 --base-url https://api.example.com/v1/
```

### 常用操作

#### 检查安装状态

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s check

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 check
```

#### 切换提供商

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s switch "提供商名称"

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 switch "提供商名称"
```

#### 添加新提供商

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s add-provider "提供商名称" "https://api.example.com/" "你的-api-密钥"

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 add-provider "提供商名称" "https://api.example.com/" "你的-api-密钥"
```

#### 列出所有提供商

```bash
# Linux/macOS
curl -L https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.sh | bash -s list-providers

# Windows
Invoke-WebRequest -Uri "https://xget.xi-xu.me/gh/xixu-me/Claude-Code-Toolkit/raw/main/cct.ps1" -OutFile "cct.ps1"; .\cct.ps1 list-providers
```

## 支持的提供商

### 内置提供商

1. **Anthropic** - 官方 Claude API
    - 使用默认的 Anthropic 端点
    - 需要官方 Anthropic API 密钥
    - 无需额外配置

2. **月之暗面 (Moonshot AI)** - 兼容 Anthropic API 且包含最新 Kimi 模型的服务
    - 已预先配置 Moonshot 端点
    - **支持最新的 Kimi 模型 (`kimi-k2-0711-preview`)**
    - 与 Anthropic API 格式完全兼容
    - 需要 Moonshot AI API 密钥

### 自定义 Anthropic 兼容提供商

您可以添加任何实现了 Anthropic 兼容端点的 API 提供商，只需指定：

- **提供商名称**: 用于识别的友好名称
- **基础 URL**: API 端点的基础 URL（必须与 Anthropic API 兼容）
- **API 密钥**: 您用于该服务的身份验证密钥

## 配置信息

### 文件位置

- **配置目录**: `~/.claude/`（Linux/macOS）或 `%USERPROFILE%\.claude\`（Windows）
- **提供商文件**: `~/.claude/providers.json`
- **Claude 配置文件**: `~/.claude.json`

### 环境变量

本工具包会自动管理以下环境变量：

- `ANTHROPIC_API_KEY`: 当前提供商的 API 密钥
- `ANTHROPIC_BASE_URL`: 自定义提供商的基础 URL（对于官方 Anthropic API 则不设置）

### 提供商配置格式

```json
{
  "提供商名称": {
    "base_url": "https://api.example.com/anthropic/",
    "api_key": "你加密后的api密钥"
  }
}
```

## 问题排查

### 常见问题

#### Node.js 版本问题

```bash
# 检查你的 Node.js 版本
node -v

# 本工具包要求 Node.js 18+
# 请从 https://nodejs.org/ 安装或更新 Node.js
```

#### npm 权限问题（Linux/macOS）

```bash
# 如果遇到权限错误，请为全局安装配置 npm
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
# 将 ~/.npm-global/bin 添加到你的 PATH 环境变量中
```

#### PowerShell 执行策略（Windows）

```powershell
# 如果无法运行脚本，请检查执行策略
Get-ExecutionPolicy

# 允许脚本执行（以管理员身份运行）
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### 获取帮助

如果您遇到问题：

1. **运行 `check` 命令** 来验证您的安装状态。
2. **查阅上方的问题排查部分**。
3. **仔细阅读错误信息** - 它们通常包含有用的信息。
4. **检查您的网络连接** 是否正常，以排除安装问题。

## 灵感与致谢

本存储库受到了 [LLM-Red-Team/kimi-cc](https://xget.xi-xu.me/gh/LLM-Red-Team/kimi-cc) 存储库的启发，该存储库提供了一种使用月之暗面（Moonshot AI）**最新 Kimi 模型（`kimi-k2-0711-preview`）** 来驱动 Claude Code 的简洁方法。我们在此基础上进行了扩展，创建了一个功能全面的跨平台工具包，支持多个 Anthropic 兼容的 API 提供商，并具备高级配置管理、提供商切换能力和稳健的安装流程。

相较于最初的灵感来源，主要增强功能包括：

- **跨平台支持**：同时适用于 Linux/macOS（Bash）和 Windows（PowerShell）。
- **多提供商管理**：可在已配置的提供商之间轻松切换。
- **持久化配置**：使用基于 JSON 的提供商存储。
- **交互式设置**：提供用户友好的提示和错误处理。
- **全面的命令集**：用于安装、更新、提供商管理和系统检查。
- **高级环境变量管理**：跨不同类型的 Shell 进行管理。

## 免责声明

本工具包按“原样”提供，不附带任何明示或暗示的保证，包括但不限于对特定用途适用性的保证。使用者需自行承担风险。作者和贡献者不对因使用本工具包或任何第三方 API 提供商而导致的任何损失、损害或问题负责。请务必查阅并遵守您所使用的任何 API 提供商的服务条款和隐私政策。

## 许可证

本仓库采用 MIT 许可证 - 详情请参阅 [LICENSE](LICENSE) 文件。
