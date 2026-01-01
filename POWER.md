---
name: "archon"
displayName: "Work with Archon Server"
description: "Archon is the command center for AI coding assistants. For you, it's a sleek interface to manage knowledge, context, and tasks for your projects. For the AI coding assistant(s), it's a Model Context Protocol (MCP) server to collaborate on and leverage the same knowledge, context, and tasks. Connect Claude Code, Kiro, Cursor, Windsurf, etc. to give your AI agents access to:
Your documentation (crawled websites, uploaded PDFs/docs)
Smart search capabilities with advanced RAG strategies
Task management integrated with your knowledge base
Real-time updates as you add new content and collaborate with your coding assistant on tasks"
keywords: ["Archon", "AI coding assistants", "Model Context Protocol", "MCP server", "knowledge management", "task management", "RAG", "semantic search", "project management platform", "open source", "beta release", "Claude Code", "Cursor integration", "Windsurf", "Supabase", "Docker", "OpenAI API", "context engineering", "AI collaboration", "repository"]
author: "Sean Wright"
---

# Work with Archon Power

Archon lets AI tools understand your project the way a senior engineer would—over time, with memory, context, and intent. It's a knowledge and task management backbone that bridges the gap between human developers and AI coding assistants.

## What Can You Do?

### 1. Manage Knowledge Base with Advanced RAG
Archon provides powerful retrieval-augmented generation capabilities:
- **Search documentation**: Find relevant information across your entire knowledge base using semantic search
- **Search code examples**: Discover code snippets and examples from indexed documentation
- **Manage knowledge sources**: Add websites, PDFs, and documentation to your knowledge base
- **Read full pages**: Access complete documentation pages with full context

**Example:** "Search the Next.js docs for server components" or "Find code examples for React hooks"

### 2. Task Management & Project Organization
Organize and track work with integrated task management:
- **Create and manage tasks**: Break down projects into actionable tasks
- **Track task status**: Follow tasks through todo → doing → review → done workflow
- **Filter and search**: Find tasks by status, project, assignee, or keyword
- **Task-driven development**: Use tasks to guide AI coding assistants through complex work

**Example:** "Create a task for implementing user authentication" or "Show me all tasks in review status"

### 3. Project Management
Structure your work with projects, features, and tasks:
- **Create projects**: Organize related work into projects
- **Manage project documents**: Store specs, designs, API docs, and guides
- **Track project features**: Monitor feature completion and status
- **Version management**: Track changes to documents and project data

**Example:** "Create a new project for the authentication system" or "List all documents for project X"

### 4. Real-Time Collaboration
Work seamlessly with AI coding assistants:
- **MCP integration**: Connect via Model Context Protocol for seamless AI tool integration
- **Real-time updates**: Get instant notifications as tasks and knowledge are updated
- **Shared context**: AI assistants access the same knowledge base and tasks you manage
- **Collaborative workflows**: AI can create tasks, search knowledge, and update project status

**Example:** "Let the AI assistant search the knowledge base for best practices" or "Have the AI create tasks for this feature"

---

## Quick Start

**Already have Archon running?** Try these commands right away:

```
"Search the knowledge base for React best practices"
"Create a task for implementing user authentication"
"List all projects"
"Show me tasks in todo status"
```

**New to Archon?** Follow the onboarding section below for complete setup.

---

## Onboarding

### Prerequisites

Before using the Work with Archon Power, ensure you have:

1. **Docker and Docker Compose**
   - Check: `docker --version` and `docker compose version`
   - Install: https://docs.docker.com/get-docker/

2. **Git**
   - Check: `git --version`
   - Install: https://git-scm.com/downloads

3. **Make** (optional, but recommended)
   - Check: `make --version`
   - Install: 
     - **macOS**: `brew install make`
     - **Linux**: Usually pre-installed
     - **Windows**: Use WSL2 or Chocolatey

### Step 1: Clone and Set Up Archon

```bash
# Clone the Archon repository
git clone https://github.com/coleam00/Archon.git
cd Archon

# Copy environment template
cp .env.example .env
```

### Step 2: Configure Environment Variables

Edit the `.env` file with your configuration:

**Required Settings:**
- `OPENAI_API_KEY`: Your OpenAI API key for embeddings and AI features
- `SUPABASE_URL`: Your Supabase project URL
- `SUPABASE_SERVICE_ROLE_KEY`: Your Supabase service role key

**Optional Settings:**
- `ARCHON_SERVER_PORT`: API server port (default: 8181)
- `ARCHON_MCP_PORT`: MCP server port (default: 8051)
- `ARCHON_UI_PORT`: Frontend UI port (default: 3737)
- `HOST`: Hostname (default: localhost)

### Step 3: Start Archon Services

**Recommended: Hybrid Development Mode**
```bash
make dev  # Backend in Docker, frontend local with hot reload
```

**Alternative: Full Docker Mode**
```bash
make dev-docker  # All services in Docker
```

**Verify services are running:**
```bash
# Check API server
curl http://localhost:8181/health

# Check MCP server (if configured)
curl http://localhost:8051/health

# Access UI
open http://localhost:3737
```

### Step 4: Configure Kiro to Use Archon MCP

The `mcp.json` file in this power directory is already configured. Ensure Archon MCP server is running on port 8051 (or your configured port).

**Verify MCP connection:**
- The MCP server should be accessible at `http://localhost:8051/mcp`
- Kiro will automatically use the configuration from `mcp.json`

---

## Available Tools

The Work with Archon Power provides these core capabilities through the MCP server:

### Knowledge Base & RAG
- **rag_search_knowledge_base** - Search your knowledge base with semantic search
- **rag_search_code_examples** - Find code examples from documentation
- **rag_get_available_sources** - List all knowledge sources
- **rag_list_pages_for_source** - Browse pages in a knowledge source
- **rag_read_full_page** - Read complete documentation pages

### Task Management
- **find_tasks** - List, search, and filter tasks
- **manage_task** - Create, update, or delete tasks
- Task status workflow: `todo` → `doing` → `review` → `done`

### Project Management
- **find_projects** - List, search, and get project details
- **manage_project** - Create, update, or delete projects
- **get_project_features** - Get features tracked in a project

### Document Management
- **find_documents** - List and search project documents
- **manage_document** - Create, update, or delete documents
- Document types: spec, design, note, prp, api, guide

### Version Management
- **find_versions** - View version history
- **manage_version** - Create snapshots or restore versions

---

## Common Workflows

### Knowledge Management
```
"Search the knowledge base for Next.js server components"
"Find code examples for React useState hooks"
"List all available knowledge sources"
"Read the full Next.js documentation page on routing"
```

### Task-Driven Development
```
"Create a task for implementing user authentication"
"Show me all tasks in todo status"
"Update task X to doing status"
"List tasks for project Y"
"Search for tasks related to authentication"
```

### Project Setup
```
"Create a new project for the authentication system"
"Add a document to project X with the API specification"
"List all projects"
"Get features for project Y"
```

### Collaborative AI Workflows
```
"Have the AI search the knowledge base for best practices before implementing"
"Create tasks for the AI to work on this feature"
"Let the AI update task status as it completes work"
```

---

## Best Practices

### Knowledge Base Management
- **Keep queries focused**: Use 2-5 keywords for best search results
- **Organize sources**: Use tags and metadata to organize knowledge sources
- **Regular updates**: Keep documentation sources up to date
- **Source filtering**: Use source_id to search within specific documentation sets

**Good queries:**
- "React useState"
- "Next.js server components"
- "FastAPI middleware"

**Avoid:**
- "How to implement React hooks useState useEffect useContext..." (too long)

### Task Management
- **Task granularity**: Create tasks that represent 30 minutes to 4 hours of work
- **Clear descriptions**: Include detailed descriptions with completion criteria
- **Status workflow**: Follow todo → doing → review → done progression
- **One active task**: Only one task should be in "doing" status at a time
- **Use features**: Group related tasks with feature labels

### Project Organization
- **Feature-specific projects**: Create granular tasks for single features
- **Codebase-wide projects**: Create feature-level tasks for entire applications
- **Document everything**: Store specs, designs, and guides as project documents
- **Track features**: Use project features to monitor component completion

### AI Collaboration
- **Research first**: Always search knowledge base before implementing
- **Task-driven**: Use tasks to guide AI through complex work
- **Update status**: Move tasks through workflow as work progresses
- **Document decisions**: Store important decisions in project documents

---

## Tips for Effective Use

1. **Use Semantic Search**: Archon's RAG capabilities work best with focused, keyword-based queries (2-5 keywords)

2. **Task-Driven Development**: Create tasks before coding to guide AI assistants through complex work

3. **Leverage Knowledge Sources**: Add your project documentation, framework docs, and best practices to the knowledge base

4. **Real-Time Collaboration**: Use the shared knowledge base and tasks to collaborate seamlessly with AI assistants

5. **Project Structure**: Organize work hierarchically: Projects → Features → Tasks

6. **Status Management**: Keep tasks moving through the workflow (todo → doing → review → done)

---

## Troubleshooting

### "Connection Refused" Errors
- Verify Archon services are running: `docker compose ps`
- Check ports are not in use: `lsof -i :8181` (or your configured ports)
- Verify `.env` configuration matches your setup
- Check Docker is running: `docker ps`

### "MCP Server Not Found"
- Ensure Archon MCP server is running on port 8051 (or configured port)
- Verify `mcp.json` points to correct URL: `http://localhost:8051/mcp`
- Check MCP server health: `curl http://localhost:8051/health`

### "No Knowledge Sources Found"
- Add knowledge sources through the Archon UI or API
- Verify Supabase connection is working
- Check that sources have been indexed (may take time for large sources)

### "Task Creation Failed"
- Verify you have a project created first
- Check task description is not empty
- Ensure required fields (project_id, title) are provided

### Docker Issues
- **Port conflicts**: Change ports in `.env` if needed
- **Permission errors** (Linux): Add user to docker group: `sudo usermod -aG docker $USER`
- **Hot reload not working**: Ensure volumes are mounted correctly in `docker-compose.yml`

### Frontend Can't Connect to Backend
- Verify backend is running: `curl http://localhost:8181/health`
- Check `ARCHON_SERVER_PORT` matches `VITE_ARCHON_SERVER_PORT` in `.env`
- Ensure CORS is configured correctly

---

## Architecture Overview

Archon uses a microservices architecture:

- **Frontend UI** (Port 3737): React + Vite web interface
- **Server** (Port 8181): FastAPI + Socket.IO for core business logic
- **MCP Server** (Port 8051): Lightweight HTTP wrapper for MCP protocol
- **Agents Service** (Port 8052): PydanticAI agent hosting (optional)
- **Database**: Supabase PostgreSQL with PGVector for embeddings

All services communicate via HTTP APIs, with Socket.IO for real-time updates.

---

## Learn More

- **Archon Repository**: https://github.com/coleam00/Archon
- **Archon Documentation**: See the README.md in the Archon repository
- **MCP Protocol**: https://modelcontextprotocol.io
- **Supabase**: https://supabase.com/docs

---

## Support

For issues with the Work with Archon Power:

1. **Check Archon Services**: Verify all services are running with `docker compose ps`
2. **Review Logs**: Check service logs with `docker compose logs -f [service-name]`
3. **Verify Configuration**: Ensure `.env` is properly configured
4. **Check MCP Connection**: Verify MCP server is accessible
5. **Review Troubleshooting**: See troubleshooting section above

For Archon-specific issues, check the [Archon GitHub Issues](https://github.com/coleam00/Archon/issues).
