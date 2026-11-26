# ConBridge for Cursor

ConBridge connects Cursor to the computers, servers and CMS sites you own.

In Cursor's Agent you can:
- read the known vulnerabilities ConBridge found;
- check that a finding applies with a read-only check;
- fix it on the one target you select.

Whether an action runs at once or waits for your approval follows the rule you set for that target in the ConBridge Console. ConBridge never changes a system by itself.

This plugin adds two things to Cursor:
- **MCP server:** the hosted ConBridge MCP server at `https://mcp.conbridge.app/mcp` (Streamable HTTP, OAuth 2.1 with PKCE).
- **Skill:** `conbridge-security`, the safe order of work for security findings.

The plugin contains no server code, credentials or tokens.

## Quick install

[![Add ConBridge MCP server to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=conbridge&config=eyJ1cmwiOiJodHRwczovL21jcC5jb25icmlkZ2UuYXBwL21jcCJ9)

Cursor shows the server before it installs it, then opens the ConBridge sign-in. No API key or header goes into any configuration: you approve the scopes on the ConBridge consent screen.

Other apps:

- **Visual Studio Code (GitHub Copilot):** [Add to Visual Studio Code](https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522conbridge%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fmcp.conbridge.app%252Fmcp%2522%257D), or from a terminal:

  ```sh
  code --add-mcp '{"name":"conbridge","type":"http","url":"https://mcp.conbridge.app/mcp"}'
  ```

- **LM Studio** (0.3.17 or later): [Add to LM Studio](https://lmstudio.ai/install-mcp?name=conbridge&config=eyJ1cmwiOiJodHRwczovL21jcC5jb25icmlkZ2UuYXBwL21jcCJ9)
- **Claude:** [Add to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=ConBridge&connectorUrl=https%3A%2F%2Fmcp.conbridge.app%2Fmcp) (opens the Add custom connector dialog with the address filled in)
- **Claude Code:**

  ```sh
  claude mcp add --transport http conbridge https://mcp.conbridge.app/mcp
  ```

  Then open `/mcp` in a Claude Code session, choose ConBridge and finish the Authenticate step.

- **Codex:**

  ```sh
  codex mcp add conbridge --url https://mcp.conbridge.app/mcp
  codex mcp login conbridge
  ```

- **Cline:** see [llms-install.md](llms-install.md).

Setup guides for every supported app: https://conbridge.app/integrations

## Requirements

- A ConBridge account ([conbridge.app](https://conbridge.app)) with at least one computer, server or site connected.
- Cursor with MCP enabled. On Business or Enterprise plans, your admin's MCP allowlist must allow this server.

## Install

1. Install **ConBridge** from the Cursor Marketplace in **Customize**.
2. Turn on the `conbridge` MCP server. Cursor opens the ConBridge sign-in and consent screen in your browser.
3. Sign in, choose the organization and the tools Cursor may use, and approve.
4. In Agent, ask for example: "Show my ConBridge security overview."

To test this plugin locally, copy this repository to `~/.cursor/plugins/local/conbridge`, then run **Developer: Reload Window**.

## Other MCP clients

The same hosted server works in other MCP apps. For Cline, see [llms-install.md](llms-install.md). Setup guides for Claude, ChatGPT, Codex, VS Code and more are at [conbridge.app/integrations](https://conbridge.app/integrations).

## Configuration

There is nothing to configure in the plugin. You choose the organization, scopes and tools on the ConBridge consent screen. You can change them later in the ConBridge Console under **AI Apps**.

## Revoke access

Revoke Cursor in the ConBridge Console under **AI Apps**, or turn single tools off for it there. Uninstall the plugin in Cursor's **Customize** as well, so Cursor stops asking to sign in.

## Security

- Every request is checked against your account, organization, the app's consent, the selected target and the tool's capability.
- A request never falls back to another computer, server or site.
- Content returned from files, logs, websites and commands is treated as data, not instructions.

Report a security issue to [security@conbridge.app](mailto:security@conbridge.app).

## Documentation and support

- [Connect ConBridge to Cursor](https://conbridge.app/integrations/cursor)
- [Tools an AI app can use](https://conbridge.app/docs/mcp/tools)
- [Scopes and revoking access](https://conbridge.app/docs/mcp/oauth)
- [Support](https://conbridge.app/support) · [support@conbridge.app](mailto:support@conbridge.app)
- [Privacy policy](https://conbridge.app/legal/privacy) · [Terms](https://conbridge.app/legal/terms)

## License

MIT. ConBridge is an Arven Soft product, operated by Mehmet Aksoy.
