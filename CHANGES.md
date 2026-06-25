# Changes from upstream Palmier Pro

protoDirector is a fork of [Palmier Pro](https://github.com/palmier-io/palmier-pro),
maintained by protoLabs and licensed under GPLv3. This file is the GPLv3 §5(a) record
of modifications made to the upstream work.

## 2026-06 — Initial fork

- **Rebrand** — Palmier Pro → protoDirector across names, the bundle identifier
  (`io.palmier.pro` → `studio.protolabs.protodirector`), the MCP server name, the
  Sparkle update feed, and user-facing strings.
- **OpenAI-compatible chat** — added an `AgentClient` that drives the in-app agent
  through any OpenAI-compatible endpoint (e.g. a self-hosted LiteLLM gateway) or a
  local model, alongside the existing Anthropic path.
- **Gateway image generation** — image generation can route through the same
  OpenAI-compatible gateway (`/v1/images/generations`) instead of the hosted backend.
- **Local-first by default** — the hosted Palmier backend (Clerk auth, Convex
  sync/credits, Sentry telemetry) is left unconfigured, so the app runs with no
  sign-in and no calls to upstream services; bring your own key or gateway.
