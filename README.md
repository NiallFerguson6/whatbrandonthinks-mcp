# What Brandon Thinks MCP and Agent Skill

Read-only [Model Context Protocol](https://modelcontextprotocol.io) server and an Agent Skill for [What Brandon Thinks](https://whatbrandonthinks.net), a private AI report on WhatsApp, iMessage, KakaoTalk, LINE, Instagram and Messenger conversations.

The server returns guides, pricing and setup links. It never receives chat content, and nothing here logs in to a messaging account.

Listed in the official MCP Registry as `net.whatbrandonthinks/chat-report`.

## Connect the MCP server

Remote endpoint (Streamable HTTP, no auth):

```
https://whatbrandonthinks.net/api/mcp
```

**Claude Code**

```bash
claude mcp add --transport http what-brandon-thinks https://whatbrandonthinks.net/api/mcp
```

**Cursor** (`~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "what-brandon-thinks": {
      "url": "https://whatbrandonthinks.net/api/mcp"
    }
  }
}
```

**Claude Desktop / claude.ai:** Settings → Connectors → Add custom connector, and paste the endpoint URL.

Clients that only support stdio can bridge with `npx -y mcp-remote https://whatbrandonthinks.net/api/mcp`.

## Tools

| Tool | What it returns |
|---|---|
| `search_guides` | Matching guides and FAQ answers on exporting and analyzing chats, privacy and limits |
| `get_pricing` | Free preview, one-time report unlock and follow-up question packs |
| `start_report` | Export steps for a platform and a setup link where the user uploads the chat |

All tools accept `locale`: `en`, `fr` or `ko`.

## Agent Skill

[`skills/what-brandon-thinks-chat-report`](skills/what-brandon-thinks-chat-report/SKILL.md) teaches an agent how to export a chat on each platform and read it carefully: what the messages show, what is a reasonable interpretation, and what a chat cannot prove. It works without the MCP server.

## Privacy

- Only analyze conversations you are part of or have a right to use.
- The tools never accept message content; uploads happen on the website.
- See the [privacy policy](https://whatbrandonthinks.net/privacy) and [how it works, its limits and refunds](https://whatbrandonthinks.net/what-brandon-thinks-review).

What Brandon Thinks is independent and not affiliated with WhatsApp, Meta, Apple, Kakao or LINE.

## License

MIT
