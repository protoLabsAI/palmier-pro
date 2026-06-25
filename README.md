<div align="center">

# protoDirector

**A local-first AI video editor.**

<a href="https://github.com/protoLabsAI/protoDirector/releases/latest/download/protoDirector.dmg">
  <img src="./assets/macos-badge.png" alt="Download protoDirector for macOS" width="180" />
</a>

<sub><i>Requires macOS 26 (Tahoe) on Apple Silicon</i></sub>

<p>
  <strong>English</strong> ·
  <a href="docs/readme/README.es.md">Español</a> ·
  <a href="docs/readme/README.zh-CN.md">简体中文</a> ·
  <a href="docs/readme/README.zh-TW.md">繁體中文</a> ·
  <a href="docs/readme/README.ja.md">日本語</a> ·
  <a href="docs/readme/README.ko.md">한국어</a> ·
  <a href="docs/readme/README.vi.md">Tiếng Việt</a> ·
  <a href="docs/readme/README.hi.md">हिन्दी</a> ·
  <a href="docs/readme/README.bn.md">বাংলা</a> ·
  <a href="docs/readme/README.ar.md">العربية</a> ·
  <a href="docs/readme/README.it.md">Italiano</a> ·
  <a href="docs/readme/README.pt-BR.md">Português (Brasil)</a> ·
  <a href="docs/readme/README.fr.md">Français</a> ·
  <a href="docs/readme/README.ru.md">Русский</a>
</p>

</div>

<img src="./assets/palmier-ui.png" alt="protoDirector UI" width="900" />

---

protoDirector is an open source video editor for Mac. You and your agent can generate and edit videos together inside the timeline.

### Swift-native video editor

We built protoDirector from scratch with Swift. The north star is Premiere Pro, with our take on integrating AI into the workflow.

### Built-in Generative AI

Generate videos and images with SOTA models like Seedance, Kling, Nano Banana Pro inside the timeline editor.

### Integrates with your agents

Connects your Claude/Codex/Cursor via MCP, or use the in-app agent to work on the same project together.

## MCP server

When the app is open, it exposes an MCP server at `http://127.0.0.1:19789/mcp` via HTTP. To connect:

**Claude Code**
```bash
claude mcp add --transport http protodirector http://127.0.0.1:19789/mcp
```

**Codex**
```bash
codex mcp add protodirector --url http://127.0.0.1:19789/mcp
```

**Cursor**

The easiest way is go inside the app `Help` -> `MCP Instructions` -> `Install in Cursor`, or install manually by adding this to `~/.cursor/mcp.json`:

```
{
  "mcpServers": {
    "protodirector": {
      "type": "http",
      "url": "http://127.0.0.1:19789/mcp"
    }
  }
}
```

**Claude Desktop**

We bundle a [mcpb](https://github.com/modelcontextprotocol/mcpb) with the app that allows a one click install Desktop Extension on Claude Desktop. Go to `Help` -> `MCP Instructions` -> `Install in Claude Desktop`

## FAQ

**Is protoDirector fully open source?**

Yes — the editor, the MCP server, and the in-app agent are all GPLv3. There is no hosted backend; generation runs through whatever OpenAI-compatible endpoint you point it at.

**Is it free?**

Yes. Download it with no login required and use it as a video editor like CapCut or Premiere, and drive it from Claude Code/Desktop or Cursor over MCP. AI chat and image generation use your own key or an OpenAI-compatible gateway you configure — there is no subscription.

**What platforms does it support?**

macOS 26 (Tahoe) on Apple Silicon only.

See [FAQ.md](FAQ.md) for more.

## Development

See [CONTRIBUTING.md](CONTRIBUTING.md)

## Support

- **Issues &amp; feedback:** Open a [GitHub Issue](https://github.com/protoLabsAI/protoDirector/issues).

## Star History

<a href="https://www.star-history.com/?type=date&repos=protoLabsAI%2Fprotodirector">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=protoLabsAI/protoDirector&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=protoLabsAI/protoDirector&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=protoLabsAI/protoDirector&type=date&legend=top-left" />
 </picture>
</a>

## License

protoDirector is free software under [GPLv3](LICENSE) — a fork of
[Palmier Pro](https://github.com/palmier-io/palmier-pro).

- Original work: Copyright (C) 2026 Palmier, Inc.
- Modifications: Copyright (C) 2026 protoLabs

Per GPLv3 the fork stays GPLv3 with full source. See [NOTICE](NOTICE) for
attribution and [CHANGES.md](CHANGES.md) for the change record. "Palmier" and
"Palmier Pro" are marks of Palmier, Inc. and are not used to endorse this fork.
