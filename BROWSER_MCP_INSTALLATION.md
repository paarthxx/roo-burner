# ByteDance UI-TARS Browser MCP Server Installation Guide

A comprehensive guide to installing and configuring the Browser MCP Server from ByteDance's UI-TARS project for web scraping and browser automation.

## 🌐 Overview

The Browser MCP Server provides powerful browser automation capabilities through the Model Context Protocol (MCP), enabling:
- **Web Scraping**: Extract content from any website
- **Dynamic Content**: Handle JavaScript-rendered pages  
- **Interactive Browsing**: Click elements, fill forms, navigate
- **Visual Capture**: Take screenshots and visual documentation
- **Cross-Platform**: Works on macOS, Windows, and Linux

## 📋 Prerequisites

- **Node.js 18+** - Required for running the MCP server
- **pnpm** - Package manager (faster than npm)
- **MCP Client** - VS Code, Cursor, Claude Desktop, or similar
- **Git** - For cloning the repository

### Install Prerequisites

```bash
# Install Node.js (if not already installed)
# Download from https://nodejs.org or use a version manager

# Install pnpm globally
npm install -g pnpm

# Verify installations
node --version  # Should be 18+
pnpm --version
```

## 🚀 Installation Steps

### 1. Clone the UI-TARS Repository

```bash
# Create directory for MCP servers (adjust path as needed)
mkdir -p /path/to/your/mcp/servers
cd /path/to/your/mcp/servers

# Clone the ByteDance UI-TARS repository
git clone https://github.com/bytedance/UI-TARS-desktop.git
cd UI-TARS-desktop
```

### 2. Install Dependencies

```bash
# Install all project dependencies (this will take a few minutes)
pnpm install

# The installation includes:
# - 2,793+ packages
# - Browser automation libraries (Puppeteer)
# - MCP SDK and related tools
# - Build tools and dependencies
```

### 3. Build the Browser MCP Server

```bash
# Navigate to the browser MCP server directory
cd packages/agent-infra/mcp-servers/browser

# Verify the build was successful (should show dist/ directory with files)
ls -la dist/

# Key files should include:
# - index.cjs (main executable, ~2.3MB)
# - server.cjs, server.js
# - Various TypeScript definitions (.d.ts files)
```

### 4. Test the Installation

```bash
# Test that the server runs correctly
node dist/index.cjs --help

# You should see usage information with all available options
```

## ⚙️ Configuration

### MCP Client Configuration

Add the browser server to your MCP client configuration file:

**For VS Code/Cursor (.roo/mcp.json):**
```json
{
  "mcpServers": {
    "browser": {
      "command": "node",
      "args": [
        "/path/to/your/mcp/servers/UI-TARS-desktop/packages/agent-infra/mcp-servers/browser/dist/index.cjs"
      ],
      "env": {}
    }
  }
}
```

**For Claude Desktop:**
```json
{
  "mcpServers": {
    "browser": {
      "command": "node", 
      "args": [
        "/path/to/your/mcp/servers/UI-TARS-desktop/packages/agent-infra/mcp-servers/browser/dist/index.cjs"
      ]
    }
  }
}
```

### Configuration Options

The browser server supports many command-line options:

```bash
# Basic usage
node dist/index.cjs

# With custom options
node dist/index.cjs --headless --viewport-size "1920,1080" --port 8089
```

**Available Options:**
- `--browser <browser>` - Choose browser: chrome, edge, firefox
- `--headless` - Run in headless mode (no GUI)
- `--viewport-size <size>` - Set browser window size (e.g., "1920,1080")
- `--port <port>` - Port for HTTP/SSE transport
- `--vision` - Enable vision mode for complex visual understanding
- `--user-agent <string>` - Custom user agent string
- `--proxy-server <proxy>` - Proxy server configuration

## 🎯 Usage Examples

### Basic Web Scraping

```javascript
// Navigate to a website
browser_navigate("https://example.com")

// Extract content as markdown
browser_get_markdown()

// Get plain text content
browser_get_text()

// Find all links on the page
browser_read_links()

// Take a screenshot
browser_screenshot("example_page")
```

### Interactive Browsing

```javascript
// Get clickable elements
browser_get_clickable_elements()

// Click on an element (use index from above)
browser_click(5)

// Fill out a form
browser_form_input_fill({
  "index": 2,
  "value": "search term",
  "clear": true
})

// Scroll the page
browser_scroll(500)  // Scroll down 500 pixels
```

### Advanced Features

```javascript
// Execute custom JavaScript
browser_evaluate("() => { return document.title; }")

// Navigate between tabs
browser_new_tab("https://another-site.com")
browser_tab_list()
browser_switch_tab(1)

// Navigate browser history
browser_go_back()
browser_go_forward()
```

## 🛠️ Available Tools

| Tool | Description | Parameters |
|------|-------------|------------|
| `browser_navigate` | Navigate to a URL | `url` |
| `browser_get_markdown` | Get page content as markdown | None |
| `browser_get_text` | Get plain text content | None |
| `browser_read_links` | Get all links on page | None |
| `browser_screenshot` | Take screenshot | `name`, `selector`, etc. |
| `browser_click` | Click an element | `index` |
| `browser_form_input_fill` | Fill form field | `index`, `value`, `clear` |
| `browser_get_clickable_elements` | Get interactive elements | None |
| `browser_evaluate` | Execute JavaScript | `script` |
| `browser_scroll` | Scroll the page | `amount` |
| `browser_new_tab` | Open new tab | `url` |
| `browser_close_tab` | Close current tab | None |
| `browser_go_back` | Go back in history | None |
| `browser_go_forward` | Go forward in history | None |

## 🔧 Troubleshooting

### Common Issues

**1. MCP Connection Errors**
```bash
# Solution: Restart your MCP client after configuration changes
# The client needs to reload the new server configuration
```

**2. Browser Launch Failures**
```bash
# Install required system dependencies
# On Ubuntu/Debian:
sudo apt-get update
sudo apt-get install -y chromium-browser

# On macOS (if using Homebrew):
brew install chromium
```

**3. Permission Issues**
```bash
# Make sure the server executable has proper permissions
chmod +x dist/*.cjs dist/*.js
```

**4. Port Conflicts (when using --port)**
```bash
# Check if port is in use
lsof -i :8089

# Kill conflicting process or choose different port
```

### Debugging

Enable debug logging:
```bash
# Set debug environment variable
DEBUG=mcp:* node dist/index.cjs
```

Test server directly:
```bash
# Run server in HTTP mode for testing
node dist/index.cjs --port 8089

# Test with curl
curl http://localhost:8089/mcp
```

## 🌟 Features

### Web Scraping Capabilities
- ✅ **JavaScript Rendering** - Handles SPAs and dynamic content
- ✅ **Multiple Content Formats** - Markdown, HTML, plain text
- ✅ **Link Extraction** - Discover site architecture  
- ✅ **Form Interaction** - Fill forms and submit data
- ✅ **Navigation** - Forward/back, multi-tab support

### Performance Features  
- ✅ **Fast & Lightweight** - Uses structured data, not pixels
- ✅ **Headless Mode** - Efficient background operation
- ✅ **Configurable** - Viewport size, user agent, proxy support
- ✅ **Screenshot Support** - Visual verification and documentation

### Advanced Features
- ✅ **Vision Mode** - AI-powered visual understanding
- ✅ **Custom JavaScript** - Execute arbitrary code in browser
- ✅ **Multi-Browser** - Chrome, Edge, Firefox support
- ✅ **Proxy Support** - Work through corporate firewalls

## 📊 System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **RAM** | 2GB | 4GB+ |
| **Storage** | 1GB | 2GB+ |
| **CPU** | 2 cores | 4+ cores |
| **Network** | Basic internet | Broadband |

## 🔗 Related Links

- **Original Repository**: https://github.com/bytedance/UI-TARS-desktop
- **MCP Protocol**: https://modelcontextprotocol.io/
- **Puppeteer Docs**: https://pptr.dev/
- **Browser MCP NPM**: https://www.npmjs.com/package/@agent-infra/mcp-server-browser

## 📝 License

This installation guide is for the ByteDance UI-TARS browser MCP server, which is licensed under MIT License. See the original repository for full license details.

## 🤝 Contributing

If you encounter issues or have improvements to this installation guide:
1. Test your changes thoroughly
2. Update documentation accordingly  
3. Submit issues to the original UI-TARS repository
4. Share installation tips and troubleshooting solutions

---

**Successfully tested on:**
- ✅ macOS Sequoia (Apple Silicon)
- ✅ Node.js 18+
- ✅ VS Code with MCP client
- ✅ pnpm package manager

*Last updated: January 2025*