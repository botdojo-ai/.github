<div align="center">
  <img src="https://www.botdojo.com/assets/images/botdojo_logo.svg" alt="BotDojo Logo" width="200" style="background-color: white; padding: 10px; border-radius: 8px;" />
  
  # BotDojo
  
  ### Build, Monitor, and Improve Production-Ready AI Agents
  
  [![Website](https://img.shields.io/badge/🌐-botdojo.com-4a3ed4?style=for-the-badge)](https://botdojo.com)
  [![Documentation](https://img.shields.io/badge/📖-docs-blue?style=for-the-badge)](https://docs.botdojo.com)
  [![Free Plan](https://img.shields.io/badge/🎉-Free_for_Developers-10b981?style=for-the-badge)](https://app.botdojo.com/signup)
  
  <p align="center">
    <strong>Enterprise-grade platform for building AI agents that deliver real business value.</strong>
    <br />
    Visual agent builder • Real-time observability • Human feedback loops • Multi-modal support
  </p>
</div>

---

## ⚡ What is BotDojo?

BotDojo is a **platform for building, running, and improving AI agents**. While our open-source SDKs help you build agentic UIs and integrate AI into your applications, the agents themselves run on the BotDojo platform — giving you enterprise-grade infrastructure for agent execution, monitoring, and continuous improvement.

### 🎯 Why BotDojo?

Building agents is just the start. Getting them to run successfully in production requires:

- **📊 Monitor Everything** — Track every agent interaction with full tracing and proactive alerts
- **🧪 Evaluate Rigorously** — Run evals offline and online to catch regressions before they ship
- **💬 Capture Human Feedback** — Turn every mistake into an improvement opportunity
- **🚀 Manage Changes Safely** — Roll out improvements with canary releases and automatic rollback

### 🔥 Key Features

<table>
  <tr>
    <td width="33%" align="center">
      <h3>🔧 Build Agents</h3>
      <p>Visual agent builder with 100+ templates, tools, and multi-modal support (chat, voice, email, SMS)</p>
    </td>
    <td width="33%" align="center">
      <h3>📊 Monitor & Evaluate</h3>
      <p>Real-time observability with tracing, evals, guardrails, and performance metrics</p>
    </td>
    <td width="33%" align="center">
      <h3>🔄 Improve Continuously</h3>
      <p>Human feedback loops that make agents smarter over time with automated rollouts</p>
    </td>
  </tr>
</table>

---

## 📦 Open Source Packages

### 🎮 [interactive-agent-sdk-playground](https://github.com/botdojo-ai/chat-sdk-playground)

**Interactive playground for building agentic UIs**

Build AI agents that see and act in your app. The SDK playground showcases chat widgets, MCP Apps, and headless integrations with live examples and real-time debugging.

```bash
# Get started in seconds
npm install -g @botdojo/cli
botdojo playground
cd sdk-playground && npm run dev
```

**Features:**
- 🚀 Chat SDK examples (inline, popup, side panel, headless)
- 🎨 Beautiful UI with three-column layout
- 🐛 Real-time debug panel for all SDK interactions
- ⚡ Pre-configured test scenarios
- 🛍️ Live demos (Bonsai Shop, Document Editor, Weather Widget)

[![npm version](https://img.shields.io/npm/v/interactive-agent-sdk-playground.svg)](https://www.npmjs.com/package/interactive-agent-sdk-playground)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

### 💬 [@botdojo/chat-sdk](https://github.com/botdojo-ai/botdojo-chat-sdk)

**Embed AI chat in any React application**

Simple React component for embedding BotDojo AI chat with custom tools, resources, and four display modes. Give your AI access to your app's data and functions.

```tsx
import { BotDojoChat } from '@botdojo/chat-sdk';

function App() {
  return (
    <BotDojoChat
      apiKey="YOUR_API_KEY"
      mode="chat-popup"
      modelContext={{
        name: 'myapp',
        tools: {
          get_data: {
            description: 'Fetch live data from your app',
            execute: async () => ({ data: 'Hello!' })
          }
        }
      }}
    />
  );
}
```

**Features:**
- 🚀 One-line integration
- 💬 Four display modes (popup, side panel, side push, inline)
- 🛠️ Custom tools that run in your app
- 📚 Resource support for serving content to AI
- 🎨 Fully customizable (colors, sizing, theming)
- 🎯 TypeScript with full type definitions
- 🖼️ MCP Apps support (interactive UI cards)
- 🎧 Headless mode for custom UIs

[![npm version](https://img.shields.io/npm/v/@botdojo/chat-sdk.svg)](https://www.npmjs.com/package/@botdojo/chat-sdk)
[![Downloads](https://img.shields.io/npm/dm/@botdojo/chat-sdk.svg)](https://www.npmjs.com/package/@botdojo/chat-sdk)

---

### 🔧 [@botdojo/cli](https://github.com/botdojo-ai/cli)

**Command-line interface for BotDojo developers**

Authenticate, manage flows, run tests, and deploy agents — all from your terminal.

```bash
npm install -g @botdojo/cli

# Setup playground
botdojo playground

# Login
botdojo login

# Clone a flow
botdojo cloneToProject botdojo.com/account/project/flow-id

# Create API key
botdojo flow api_key create <flow-id>
```

**Commands:**
- 🔐 Authentication (`login`, `logout`, `status`, `switch`)
- 📁 Project management (`project create`)
- 🔄 Flow management (`clone`, `list`, `get`, `pull-from-origin`)
- 🔑 API key management (`api_key create`, `list`, `archive`)
- 🏃 Local development (`run`, `pull`, `checkout`, `publish`, `diff`)
- 🔍 Debugging (`flow_request get`, `get_trace`, `repl`)

[![npm version](https://img.shields.io/npm/v/@botdojo/cli.svg)](https://www.npmjs.com/package/@botdojo/cli)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

### 🎨 [mcp-app-view](https://github.com/botdojo-ai/mcp-app-view)

**Build and embed MCP Apps (SEP-1865) — Interactive UIs for AI agents**

Framework-agnostic SDK for building MCP Apps that work with any MCP-compatible host. Created by BotDojo as an open-source contribution to the MCP ecosystem.

```tsx
import { useMcpApp } from 'mcp-app-view/react';

function MyMcpApp() {
  const { isInitialized, state, sendMessage, callTool } = useMcpApp({
    initialState: { counter: 0 }
  });

  return (
    <div>
      <h1>Counter: {state.counter}</h1>
      <button onClick={() => sendMessage([{ type: 'text', text: 'Hello!' }])}>
        Send to Agent
      </button>
    </div>
  );
}
```

**Features:**
- ✅ SEP-1865 compliant (official MCP Apps spec)
- ✅ Framework agnostic (works with any framework or vanilla JS)
- ✅ Optional React support (hooks and components)
- ✅ Zero runtime dependencies
- ✅ TypeScript first with full type safety
- ✅ Built-in state management
- ✅ `McpProxyHost` component for embedding MCP Apps

[![npm version](https://img.shields.io/npm/v/mcp-app-view.svg)](https://www.npmjs.com/package/mcp-app-view)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

### ⚙️ [@botdojo/sdk](https://github.com/botdojo-ai/sdk)

**Run BotDojo AI flows with custom tools and real-time streaming**

Core SDK for running BotDojo agents with dynamic tool integration and streaming callbacks.

```typescript
import { BotDojoSDK } from '@botdojo/sdk';

const client = new BotDojoSDK({
  apiKey: 'your-api-key'
});

const result = await client.runFlow(
  { text_input: 'Hello!' },
  {
    callbacks: {
      onNewToken: (token) => process.stdout.write(token.token),
      onStepUpdate: (step) => console.log(step.stepLabel)
    }
  }
);
```

**Features:**
- 🔄 Real-time streaming with callbacks
- 🛠️ Dynamic MCP tool integration
- 📡 Session management
- 🔐 Secure API key authentication
- 📊 Step-by-step observability
- ⚡ Fast and lightweight

[![npm version](https://img.shields.io/npm/v/@botdojo/sdk.svg)](https://www.npmjs.com/package/@botdojo/sdk)

---

## 🎓 Learning Resources

<table>
  <tr>
    <td width="50%">
      <h3>📖 Documentation</h3>
      <p>Comprehensive guides, API references, and tutorials</p>
      <a href="https://docs.botdojo.com">docs.botdojo.com →</a>
    </td>
    <td width="50%">
      <h3>🌐 Website</h3>
      <p>Learn about the platform, pricing, and enterprise solutions</p>
      <a href="https://botdojo.com">botdojo.com →</a>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>🎮 SDK Playground</h3>
      <p>Interactive examples and live demos</p>
      <a href="https://github.com/botdojo-ai/chat-sdk-playground">View on GitHub →</a>
    </td>
    <td width="50%">
      <h3>💡 Blog & Tutorials</h3>
      <p>Best practices and integration guides</p>
      <a href="https://botdojo.com/blog">Read the blog →</a>
    </td>
  </tr>
</table>

---

## 🚀 Quick Start

Get started with BotDojo in under 5 minutes:

```bash
# 1. Install the CLI
npm install -g @botdojo/cli

# 2. Setup the playground
botdojo playground

# 3. Start the dev server
cd sdk-playground
npm run dev

# 4. Open http://localhost:3500 and start building!
```

**Want to embed chat in your app?**

```bash
npm install @botdojo/chat-sdk react
```

```tsx
import { BotDojoChat } from '@botdojo/chat-sdk';

<BotDojoChat apiKey="YOUR_KEY" />
```

---

## 🎉 Free Developer Plan

Get started with the Interactive Agent SDK for free. Build and deploy AI agents with full access to monitoring, evals, and feedback tools.

**✨ Free plan includes:**
- ✅ Visual agent builder with 100+ templates
- ✅ All open-source SDKs (`@botdojo/chat-sdk`, `@botdojo/cli`, `mcp-app-view`)
- ✅ Real-time observability and tracing
- ✅ Experiment management and prompt iteration
- ✅ Guardrails and cost analytics
- ✅ Multi-modal support (chat, voice, email, SMS)

[**Get Started Free →**](https://app.botdojo.com/signup)

---

## 🤝 Contributing

We welcome contributions! Each package has its own contributing guidelines:

- [@botdojo/chat-sdk Contributing](https://github.com/botdojo-ai/botdojo-chat-sdk/blob/main/CONTRIBUTING.md)
- [@botdojo/cli Contributing](https://github.com/botdojo-ai/cli/blob/main/CONTRIBUTING.md)
- [mcp-app-view Contributing](https://github.com/botdojo-ai/mcp-app-view/blob/main/CONTRIBUTING.md)

---

## 📄 License

All packages are MIT licensed. See individual package repositories for details.

---

## 🔗 Links

<p align="center">
  <a href="https://botdojo.com">🌐 Website</a> •
  <a href="https://docs.botdojo.com">📖 Documentation</a> •
  <a href="https://app.botdojo.com">🚀 Get Started</a> •
  <a href="https://botdojo.com/pricing">💰 Pricing</a> •
  <a href="https://twitter.com/botdojo">🐦 Twitter</a> •
  <a href="https://discord.gg/botdojo">💬 Discord</a> •
  <a href="https://github.com/botdojo-ai">💻 GitHub</a>
</p>

---

<div align="center">
  <p><strong>Built with ❤️ by the BotDojo team</strong></p>
  <p>
    <a href="https://botdojo.com">botdojo.com</a> • 
    Made for developers who want to build production-ready AI agents
  </p>
</div>
