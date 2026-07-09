# OpenCode Alpine Linux

Alpine Linux packages for [OpenCode](https://github.com/anomalyco/opencode) - the open source AI coding agent.

## Features

- **100% Offline**: Built from source, no internet required after installation
- **All Plugins Included**: Feature-dev, code-review, security-guidance, commit-commands, frontend-design
- **Native Binary**: Compiled standalone executable
- **Auto-start**: OpenCode starts automatically on login

## Packages

### opencode
Main OpenCode package built from source.

**Version:** 1.17.15  
**Dependencies:** git  
**Build Dependencies:** bun, nodejs, npm, python3, make, g++

## Installation

```bash
# Install from repository
apk add opencode

# Or build from source
abuild -r
```

## Configuration

Default configuration is installed at `/etc/opencode/config.json`.

### Environment Variables

| Variable | Purpose |
|----------|---------|
| `ANTHROPIC_API_KEY` | For Claude models |
| `OPENAI_API_KEY` | For OpenAI models |
| `GEMINI_API_KEY` | For Google Gemini models |
| `GITHUB_TOKEN` | For GitHub Copilot models |

## Usage

```bash
# Start OpenCode
opencode

# Start with debug logging
opencode -d

# Run single prompt
opencode -p "Explain the use of context in Go"
```

## Plugins

### Feature Development
7-phase workflow for building features.

**Command:** `/feature-dev`

### Code Review
Automated PR code review with confidence scoring.

**Command:** `/code-review`

### Security Guidance
Security review with pattern warnings and LLM review.

### Commit Commands
Git workflow automation.

**Commands:** `/commit`, `/commit-push-pr`, `/clean_gone`

### Frontend Design
Create distinctive, production-grade frontend interfaces.

## Building ISO

GitHub Actions workflow is included to build an Alpine ISO with OpenCode pre-installed.

1. Go to Actions tab
2. Run "Build OpenCode Alpine ISO" workflow
3. Download artifact

## License

MIT