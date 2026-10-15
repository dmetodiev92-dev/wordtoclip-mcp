# WordToClip MCP server

Use an AI assistant to search what Andrew Tate actually said. WordToClip indexes the transcripts of **1,681 publicly posted videos (about 1,190 hours, 11.8 million words)**. Every word has a timestamp, so your assistant can:
- find a phrase;
- quote it with the exact second and a link to that moment;
- read the transcript around it;
- and, if you ask, cut it into a vertical short.

- **Server URL:** `https://mcp.wordtoclip.com/mcp`
- **Transport:** Streamable HTTP (remote, nothing to install)
- **Auth:** OAuth (sign in with your WordToClip account), or `Authorization: Bearer <key>` with a key from <https://www.wordtoclip.com/account/assistant>
- **Docs:** <https://www.wordtoclip.com/mcp> · LLM docs: <https://www.wordtoclip.com/llms-full.txt>
- **Registry:** `com.wordtoclip/mcp` in the official MCP Registry

This repository only documents the hosted server; the server itself is not open source.

## Tools (34)

| Group | Tools |
|---|---|
| Search | `search_moments`, `similar_moments`, `highlights`, `trending` |
| Transcripts | `get_transcript`, `list_videos`, `get_video` |
| Options | `list_presets`, `list_music`, `list_effects`, `list_caption_styles`, `list_my_images` |
| Build | `create_project`, `add_clips`, `remove_clip`, `delete_project`, `get_project`, `list_projects`, `set_project_options`, `set_clip_images`, `set_clip_framing`, `upload_image`, `upload_music` |
| Price & render | `price_export`, `render_clip`, `render_project`, `render_status`, `list_renders`, `download_url` |
| Alerts & account | `list_alerts`, `add_alert`, `remove_alert`, `alert_matches`, `whoami` |

The server shows the price before it spends any credits, and it renders only after you confirm.

## Connect

**Claude (claude.ai / Desktop):** Settings → Connectors → Add custom connector. Use the name `WordToClip` and the URL `https://mcp.wordtoclip.com/mcp`, then sign in with WordToClip and approve.

**Claude Code:**

```sh
claude mcp add wordtoclip --transport http https://mcp.wordtoclip.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "wordtoclip": {
      "url": "https://mcp.wordtoclip.com/mcp",
      "headers": { "Authorization": "Bearer YOUR_KEY" }
    }
  }
}
```

**ChatGPT (developer mode):** Settings → Developer mode → create an app. Use the URL `https://mcp.wordtoclip.com/mcp` with OAuth.

## Try it

- "Find where Andrew Tate talks about discipline and give me the three clearest quotes with links."
- "Did Andrew Tate ever say 'what color is your Bugatti'? Show me the exact moment."
- "Make a 9:16 clip of that moment with captions, and tell me the price first."

## Plans

- **Free on the website, without an account:** search, full transcripts, topic pages and 30-second previews.
- **Assistant access (MCP):** needs the Pro plan; see <https://www.wordtoclip.com/pricing>.
- **Researchers:** can ask for free access; see <https://www.wordtoclip.com/research>.

## Notes

- Transcripts are made automatically by speech recognition and can contain mistakes. Every result links to the audio, so you can check it.
- WordToClip is independent and unofficial. It is not affiliated with, endorsed by or operated by Andrew Tate.
- Contact: support@wordtoclip.com
