# Rexi downloads

Installers for **Rexi**, a friendly guard for AI agents. Rexi sits on your Mac or PC, watches what AI agents try to do, quietly blocks the dangerous moves, and only asks you when a decision is really yours.

## Get the latest version

| Your computer | Download |
| --- | --- |
| Mac with Apple silicon (M1 or newer) | [Rexi-0.1.4-arm64.dmg](https://github.com/RexiHQ/releases/releases/download/v0.1.4/Rexi-0.1.4-arm64.dmg) |
| Mac with an Intel chip | [Rexi-0.1.4.dmg](https://github.com/RexiHQ/releases/releases/download/v0.1.4/Rexi-0.1.4.dmg) |
| Windows 10 or 11, 64-bit | [Rexi-Setup-0.1.4.exe](https://github.com/RexiHQ/releases/releases/download/v0.1.4/Rexi-Setup-0.1.4.exe) |

Macs need macOS 13 or later. Every version is listed under [Releases](https://github.com/RexiHQ/releases/releases).

## Activate and start protection

Open Rexi and choose **Open Rexi Devices**. Sign in to your verified account, register or select this computer, then choose **Get desktop activation code**. Paste the code into Rexi within ten minutes. Open **My agents** and turn on the Claude Code live guard. Start a new Claude Code session to see checked actions in Activity. [Manage devices](https://tryrexi.com/my/devices)

## This is a preview

Preview builds are not yet signed with a publisher certificate, so macOS and Windows show a warning the first time you open them. Signed installers arrive with the beta. If you would rather wait for those, that is a perfectly sensible choice.

Each release lists SHA-256 checksums so you can check that a download arrived intact.

## Rexi API, MCP server and CLI

Rexi provides AI agent security for Mac and Windows. Its Claude Code guard checks tool calls locally. The public information service lets developers look up installer URLs, pricing and supported platforms without accessing a desktop installation. [Rexi website](https://tryrexi.com/) · [Rexi API documentation](https://tryrexi.com/docs) · [OpenAPI specification](https://tryrexi.com/openapi.json)

To connect an MCP client, select Streamable HTTP and enter `https://tryrexi.com/mcp`. The server accepts anonymous requests. Use `get_downloads` to retrieve the current version and official installers. [Rexi MCP server card](https://tryrexi.com/.well-known/mcp/server-card.json)

To use the CLI with Node.js 18 or later, install the client from this repository and request the installer list.

```sh
npm install github:RexiHQ/releases
npx arcnin-info downloads
```

The same package exposes a JavaScript client for the public API.

```js
import { getArcninInformation } from 'arcnin-public-information';
const { installers } = await getArcninInformation('downloads');
```

Agents can use the [Rexi public information skill](skills/arcnin-public-information/SKILL.md) to match an installer to a computer, check plan availability, or look up live guard support.

```sh
npx skills add Rexi/releases --skill arcnin-public-information
```
