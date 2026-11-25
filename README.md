# NoviHome connector plugin

A Cursor (and Grok) plugin that connects to the official NoviHome MCP server at `https://ai.novihome.com/mcp`. After a NoviHome builder staff account signs in, the assistant can help with buyers, listings, communities, agreements, change orders, tasks, reports, and related NoviHome work.

This repository is the plugin package (manifest, MCP config, logo, and docs). It does not contain the NoviHome MCP server source.

## Marketplace listings

This repository is the source for the Cursor Marketplace and Grok listings. `.cursor-plugin/` is Cursor's manifest. Manifests for other marketplaces can be added alongside it.

## Who can connect

NoviHome builder staff with access to at least one builder, and with an allowed staff role (for example Admin, Content, Clients, Rep, Follower, Deployer, Legal, or Marketing). Buyer accounts and partner-only (buyer agent) accounts cannot connect.

## What it can do

The connector exposes tools across these areas:

- **Session and account:** current user, staff profiles, and session refresh
- **Buyers and co-buyers:** look up and update clients, notes, documents, images, teams, chats, and welcome email
- **Listings and inventory:** listings, communities, floor plans, incentives, lenders, listing files, documents, and images
- **Agreements:** templates, assignment, and agreement details (some template actions require a Legal Administrator role and Legal to be enabled for the builder)
- **Change orders:** create and update change orders, lines, notes, photos, and status (the builder must have Change Orders enabled)
- **Tasks:** tasks, locations, notes, photos, status, and task reports (the builder must have Tasks enabled)
- **Communications:** buyer and cobuyer messages, blasts, and related chat reports
- **Staff and reports:** staff lists, pipeline, registration, pulse surveys, and activity reports
- **Memories:** save, list, and delete assistant memories for the builder
- **Feedback:** optional product feedback, which previews the text and requires confirmation before it is stored

Exact tool availability follows the signed-in user's NoviHome role and the builder's enabled features. Anything that reaches a buyer is previewed and sent only after you approve it.

## Install and sign in

1. Install this plugin from the [Cursor Marketplace](https://cursor.com/marketplace) once it is listed, or test a local copy by placing this folder at `~/.cursor/plugins/local/novihome` and reloading Cursor.
2. Open **Customize** and enable the NoviHome MCP server if it is not already on.
3. When prompted to authenticate, complete NoviHome sign-in and consent in the browser. You should not need to paste an API token. The server uses OAuth 2.0 authorization code with PKCE, refresh tokens, and dynamic client registration.
4. After you are connected, ask the assistant to do NoviHome work (for example, list your communities or look up a buyer).

The production MCP endpoint configured in [`mcp.json`](mcp.json) is:

```text
https://ai.novihome.com/mcp
```

## Disconnect

In NoviHome Portal, go to **My settings → Connected apps** and choose **Disconnect**. That revokes the connection, generally within about 30 seconds.

## Privacy, terms, and support

Use of the connector is covered by NoviHome's legal pages, including a section on the MCP connector:

- [Privacy Policy](https://legal.novihome.com/privacy)
- [Terms of Use](https://legal.novihome.com/terms)

Product support: [support@novihome.com](mailto:support@novihome.com)

Tool results can include builder data and are sent to the AI provider you use. Review proposed write actions before you confirm them.

## License

This plugin package is licensed under the [MIT License](LICENSE). Copyright 2026 NoviHome, LLC.
