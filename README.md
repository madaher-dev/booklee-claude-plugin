# Booklee for Claude

Booklee's plugin connects to the hosted Booklee MCP server and includes account connection, appointment, and business workflows. Public discovery is anonymous; protected actions use Booklee OAuth and your selected access.

## Connect the Booklee service

In Claude **Settings → Connectors**, add a custom connector named **Booklee** with the server URL below. If your organization manages connectors, an administrator may need to add it before you can connect your account. This connector-only setup provides Booklee tools; it does not install the workflows bundled in this ZIP.

When Claude asks you to connect Booklee, finish Booklee sign-in in the browser. On the `/mcp/authorize` consent screen, choose the capabilities, organizations, and locations the assistant may access, then click **Allow**. Return to Claude and enable the Booklee connector for your conversation. Public location browsing does not require Booklee sign-in; personal and business actions require your approved account connection.

Ask Claude to show your approved Booklee account and business access. The connection workflow calls `get_access_context` to verify the current account, role, and delegated targets. A successful sign-in screen or an installed package alone does not verify that a protected tool can run.

## Add the optional Booklee workflows

In Claude, open **Customize → Plugins** and upload the Booklee Claude plugin ZIP. The package includes account connection, customer appointment, and business operations workflows, plus the Booklee MCP connection configuration. Plugin availability depends on your plan and organization settings. Complete Booklee OAuth if Claude prompts you after installation; the ZIP contains no credentials.

Start a new conversation with Booklee enabled. Use Claude's `/` or **+** menu to find the installed Booklee skills, or ask Claude directly:

- **Customer:** “Show my personal upcoming Booklee appointments.”
- **Business owner:** “Summarize this week's business appointments at my selected location.”

For setup details, see the [Claude custom connector guide](https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp) and [Claude plugin guide](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

## Environment and access

This source package points to **production** at `https://booklee.app/api/mcp`. Production MCP activation and public directory review are separate release steps. A package existing in this repository does not mean its production endpoint is enabled or the plugin is listed in a provider directory.

This directory source contains the production plugin only. Keep any separate staging connection on its own staging endpoint and do not reuse tokens across environments.

Disconnect access at https://booklee.app/mcp/connections or from Booklee account settings. Remove the installed plugin separately in the client if you no longer want its skills.

Publisher: Booklee. Support: https://booklee.app/contact. Privacy: https://booklee.app/privacy. Terms: https://booklee.app/terms.

The plugin and its bundled assets are proprietary to Booklee. See LICENSE for permitted use. Provider names identify compatibility; this package does not claim endorsement by OpenAI or Anthropic.
