# FlexWurx

Connects Claude to FlexWurx: the contracts and insurance compliance records of the organizations you can access, their properties, tenants and subs (vendors), and each contract's stored text. The plugin adds the FlexWurx connector and a skill that teaches Claude to use it well: asking which entity you mean when a name is unclear, reading a contract whole, citing the contract and the page for every answer, and getting a document query right before starting it.

## Use it

Connect the FlexWurx connector from the plugin's Connectors tab and sign in with your FlexWurx account. Then ask Claude about your contracts, tenants, vendors and properties, and their insurance requirements. Claude sees only what your FlexWurx account can access.

## Data

The plugin runs nothing and sends nothing itself. Its connector sends each request to FlexWurx's MCP server at https://mcp.flexwurx.com/mcp, signed in as you, and answers only with data your FlexWurx account can access.

## License

The plugin is proprietary and licensed under LICENSE, for FlexWurx users only; questions go to legal@flexwurx.com.

## Source

This plugin is published from its own public GitHub repository. Its source, the skill included, lives in FlexWurx's monorepo beside the MCP server it uses.
