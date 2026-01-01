# Archon Power for Kiro

A Kiro Power that integrates [Archon Server](https://github.com/coleam00/Archon) - the knowledge and task management backbone for AI coding assistants.

## What is Archon?

Archon is a command center for AI coding assistants that provides:
- **Knowledge Management**: Advanced RAG capabilities for searching documentation and code examples
- **Task Management**: Integrated task tracking with project organization
- **MCP Integration**: Model Context Protocol server for seamless AI tool integration
- **Real-Time Collaboration**: Shared context between developers and AI assistants

## Features

This power enables Kiro to:
- Search your knowledge base using semantic search
- Manage tasks and projects
- Access documentation and code examples
- Collaborate with AI assistants on shared tasks and knowledge

## Installation

1. Ensure Archon Server is running (see [POWER.md](./POWER.md) for setup instructions)
2. This power includes the MCP configuration needed to connect Kiro to Archon
3. Kiro will automatically detect and use this power when Archon-related keywords are mentioned

## Configuration

The `mcp.json` file is pre-configured to connect to Archon's MCP server at `http://localhost:8051/mcp`. If you're running Archon on a different port or hostname, update the configuration accordingly.

## Usage

Once installed, you can use natural language commands like:
- "Search the knowledge base for React best practices"
- "Create a task for implementing user authentication"
- "List all projects"
- "Show me tasks in todo status"

See [POWER.md](./POWER.md) for complete documentation and examples.

## Learn More

- [Archon Repository](https://github.com/coleam00/Archon)
- [Kiro Powers Documentation](https://kiro.dev/docs/powers/create/)
