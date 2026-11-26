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

## Requirements

- A ConBridge account ([conbridge.app](https://conbridge.app)) with at least one computer, server or site connected.
- Cursor with MCP enabled. On Business or Enterprise plans, your admin's MCP allowlist must allow this server.

## Install

1. Install **ConBridge** from the Cursor Marketplace in **Customize**.
2. Turn on the `conbridge` MCP server. Cursor opens the ConBridge sign-in and consent screen in your browser.
3. Sign in, choose the organization and the tools Cursor may use, and approve.
4. In Agent, ask for example: "Show my ConBridge security overview."

To test this plugin locally, copy this repository to `~/.cursor/plugins/local/conbridge`, then run **Developer: Reload Window**.

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
