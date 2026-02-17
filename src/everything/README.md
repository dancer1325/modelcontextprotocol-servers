# Everything MCP Server
**[Architecture](docs/architecture.md)
| [Project Structure](docs/structure.md)
| [Startup Process](docs/startup.md)
| [Server Features](docs/features.md)
| [Extension Points](docs/extension.md)
| [How It Works](docs/how-it-works.md)**


* == MCP server /
  * goal
    * 💡exercise ALL MCP protocol's features💡
      * -- by -- implementing
        * prompts
        * tools
        * resources
        * sampling
        * ...
  * ❌NOT goal❌
    * useful server
  * use cases
    * test server -- for -- MCP clients builders

## Tools, Resources, Prompts, and Other Features

* [here](docs/features.md)

## how to use with
### Claude Desktop?

* recommendations
  * use [stdio Transport](https://modelcontextprotocol.io/specification/2025-03-26/basic/transports#stdio)

* steps
  * | "claude_desktop_config.json",
    * add 

  ```json
  {
    "mcpServers": {
      "everything": {
        "command": "npx",
        "args": [
          "-y",
          "@modelcontextprotocol/server-everything"
        ]
      }
    }
  }
  ```

### VS Code?

* TODO: For quick installation, use of of the one-click install buttons below...

[![Install with NPX in VS Code](https://img.shields.io/badge/VS_Code-NPM-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=everything&config=%7B%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40modelcontextprotocol%2Fserver-everything%22%5D%7D) [![Install with NPX in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-NPM-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=everything&config=%7B%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40modelcontextprotocol%2Fserver-everything%22%5D%7D&quality=insiders)

[![Install with Docker in VS Code](https://img.shields.io/badge/VS_Code-Docker-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=everything&config=%7B%22command%22%3A%22docker%22%2C%22args%22%3A%5B%22run%22%2C%22-i%22%2C%22--rm%22%2C%22mcp%2Feverything%22%5D%7D) [![Install with Docker in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Docker-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=everything&config=%7B%22command%22%3A%22docker%22%2C%22args%22%3A%5B%22run%22%2C%22-i%22%2C%22--rm%22%2C%22mcp%2Feverything%22%5D%7D&quality=insiders)

For manual installation, you can configure the MCP server using one of these methods:

**Method 1: User Configuration (Recommended)**
Add the configuration to your user-level MCP configuration file
* Open the Command Palette (`Ctrl + Shift + P`) and run `MCP: Open User Configuration`
* This will open your user `mcp.json` file where you can add the server configuration.

**Method 2: Workspace Configuration**
Alternatively, you can add the configuration to a file called `.vscode/mcp.json` in your workspace
* This will allow you to share the configuration with others.

> For more details about MCP configuration in VS Code, see the [official VS Code MCP documentation](https://code.visualstudio.com/docs/copilot/customization/mcp-servers).

#### NPX

```json
{
  "servers": {
    "everything": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-everything"]
    }
  }
}
```

## ways to run
### from source -- with -- [HTTP+SSE Transport](https://modelcontextprotocol.io/specification/2024-11-05/basic/transports#http-with-sse)
* | [2025-03-26](https://modelcontextprotocol.io/specification/2025-03-26/basic/transports),
  * ⚠️deprecated⚠️ 

```shell
cd src/everything
npm install
npm run start:sse
```

## from source -- with -- [Streamable HTTP Transport](https://modelcontextprotocol.io/specification/2025-03-26/basic/transports#streamable-http)

```shell
cd src/everything
npm install
npm run start:streamableHttp
```

### -- as an -- installed package
* steps

  ```shell
  # 1. install
  npm install -g @modelcontextprotocol/server-everything@latest
  
  # 2. run stdio server
  # 2.1 WITHOUT specifying    -- Reason: it's default one --
  npx @modelcontextprotocol/server-everything
  # 2.2 specifying it
  npx @modelcontextprotocol/server-everything stdio
    
  # 3. run SSE server
  npx @modelcontextprotocol/server-everything sse
  
  # 4. run the streamable HTTP server
  npx @modelcontextprotocol/server-everything streamableHttp
  ````
