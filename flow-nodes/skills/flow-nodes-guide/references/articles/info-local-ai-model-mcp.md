# Local AI Model via MCP

Source route: `/docs/info/local-ai-model-mcp`. Media is not bundled; public route availability must be verified.

Flow Nodes includes an MCP (Model Context Protocol) server that can be used with local AI models.

> **Note**
>
> The MCP is only for **macOS**

> **Tip**
>
> To use Flow Nodes MCP with **Claude** and **Codex**, see the commands in Flow Nodes settings.

# Requirements

- Flow Nodes running on macOS with an open Flow
- [Ollama](https://ollama.com) or similar
- [Kit](https://github.com/mark3labs/kit), [mcphost](https://github.com/mark3labs/mcphost) or similar
- `qwen3:14b` or similar *(the local AI model)*

# **1. Install Ollama**

```bash
brew install ollama
```

Start Ollama before downloading the model. If you installed it with Homebrew, run `ollama serve` in a separate terminal.

Download the model:

```bash
ollama pull qwen3:14b
```

Verify:

```bash
ollama run qwen3:14b
```

Ollama runs locally at:

```text
http://localhost:11434
```

# **2. Install Kit**

Install Go:

```bash
brew install go
```

Install Kit:

```bash
go install github.com/mark3labs/kit/cmd/kit@latest
```

Add to PATH with bash:

```bash
echo 'export PATH="$PATH:$(go env GOPATH)/bin"' >> ~/.bash_profile
source ~/.bash_profile
```

Add to PATH if using zsh:

```bash
echo 'export PATH="$PATH:$(go env GOPATH)/bin"' >> ~/.zshrc
source ~/.zshrc
```

Verify:

```bash
which kit
kit --help
```

# **3. Configure Flow Nodes MCP**

Create the Kit config:

```bash
vi ~/.kit.yml
```

Add in vim (enter insert mode with `i`):

```yaml
model: ollama/qwen3:14b

mcpServers:
  flownodes:
    type: local
    command:
      - "/Applications/Flow Nodes.app/Contents/Resources/MCP/FlowNodesMCP"
```

Write and exit vim with `:wq`

# **4. Start Flow Nodes**

Open Flow Nodes.

Open or create a new flow.

Make sure the MCP is active in settings.

# **5. Start Kit**

Run:

```bash
kit
```

If successful, Kit should show:

```text
MCP server 'flownodes' loaded with XX tools
```

# **6. Test with a Prompt**

```text
create a circle node
```

# **Architecture**

Ollama (qwen3:14b)  
↑↓  
Kit  
↑↓  
FlowNodesMCP  
↑↓  
Flow Nodes

See the [Kit configuration reference](https://github.com/mark3labs/kit#configuration) and [Ollama documentation](https://docs.ollama.com/quickstart) for installation details.
