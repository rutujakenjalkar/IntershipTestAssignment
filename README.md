<a href="https://mcp.scira.ai">
  <h1 align="center">MCP UI Playground Chat (Scira MCP Chat Fork)</h1>
</a>

<p align="center">

  This Scira Chat fork hosts a playground for [MCP-UI](https://github.com/idosal/mcp-ui)-enabled chats. The chat automatically renders tool call results from the `mcp-ui` server SDK as UI components and can react to actions performed on them. For more information, please refer to the [documentation](https://idosal.github.io/mcp-ui/).

  You can define any MCP server to see the results live. For your convenience, you can configure the [demo server](https://remote-mcp-server-authless.idosalomon.workers.dev/sse) as a quickstart (see more details in the [guide](https://github.com/idosal/mcp-ui?tab=readme-ov-file#-examples)).
</p>

<p align="center">
  <a href="#features"><strong>Features</strong></a> •
  <a href="#mcp-server-configuration"><strong>MCP Configuration</strong></a> •
  <a href="#license"><strong>License</strong></a>
</p>
<br/>

## Features

- **Supports UI in tool responses using `mcp-ui`**!
- Streaming text responses powered by the [AI SDK by Vercel](https://sdk.vercel.ai/docs), allowing multiple AI providers to be used interchangeably with just a few lines of code.
- Full integration with [Model Context Protocol (MCP)](https://modelcontextprotocol.io) servers to expand available tools and capabilities.
- Multiple MCP transport types (HTTP, SSE and stdio) for connecting to various tool providers.
- Built-in tool integration for extending AI capabilities.
- Reasoning model support.
- [shadcn/ui](https://ui.shadcn.com/) components for a modern, responsive UI powered by [Tailwind CSS](https://tailwindcss.com).
- Built with the latest [Next.js](https://nextjs.org) App Router.

## MCP Server Configuration

This application supports connecting to Model Context Protocol (MCP) servers to access their tools. You can add and manage MCP servers through the settings icon in the chat interface.

### Adding an MCP Server

1. Click the settings icon (⚙️) next to the model selector in the chat interface.
2. Enter a name for your MCP server.
3. Select the transport type:
   - **HTTP or SSE (Server-Sent Events)**: For HTTP-based remote servers
   - **stdio (Standard I/O)**: For local servers running on the same machine

#### HTTP or SSE Configuration

If you select HTTP / SSE transport:
1. Enter the server URL (e.g., `https://mcp.example.com/mcp` or `https://mcp.example.com/token/sse`)
2. Click "Add Server"

#### stdio Configuration

If you select stdio transport:
1. Enter the command to execute (e.g., `npx`)
2. Enter the command arguments (e.g., `-y @modelcontextprotocol/server-google-maps`)
   - You can enter space-separated arguments or paste a JSON array
3. Click "Add Server"

4. Click "Use" to activate the server for the current chat session.

### Available MCP Servers

You can use any MCP-compatible server with this application. You can use the [demo server](https://remote-mcp-server-authless.idosalomon.workers.dev/sse), which exposes 4 tools -
- `get_tasks_status` - Get a textual representation of the status of all tasks. Used to highlight the difference from UI tool results.
- `show_task_status` - Displays a UI for the user to see the status of tasks (as opposed to text).
- `show_user_status` - Displays a UI for the user to see the status of a user and their tasks (triggered by clicking on the user avatar in the `show_task` UI).
- `nudge_team_member` - Nudges team member (triggered by clicking `Nuge` on the `user_status` UI).
You can use any MCP-compatible server with this application. Here are some examples:

- [Composio](https://composio.dev/mcp) - Provides search, code interpreter, and other tools
- [Zapier MCP](https://zapier.com/mcp) - Provides access to Zapier tools
- [Hugging Face MCP](https://huggingface.co/mcp) - Provides tool access to Hugging Face Hub
- Any MCP server using stdio transport with npx and python3

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.
