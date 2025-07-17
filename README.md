[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/jackkuo666-pypi-mcp-server-badge.png)](https://mseep.ai/app/jackkuo666-pypi-mcp-server)

# PyPI MCP Server

🔍 Enabling AI assistants to search and access PyPI package information through a simple MCP interface.

PyPI MCP Server provides a bridge to the PyPI package repository for AI assistants through the Model Context Protocol (MCP). It allows AI models to programmatically search Python packages and access their metadata, supporting features like retrieving package information, searching packages, viewing version history, and download statistics.

## ✨ Core Features
- 🔎 Package Search: Query PyPI packages by keywords ✅
- 📊 Metadata Access: Get detailed metadata for specific packages ✅
- 📦 Version Information: Get all released versions of a package ✅
- 📈 Statistics Data: Get download statistics for packages ✅
- 🚀 Efficient Retrieval: Fast access to package information ✅

## 🚀 Quick Start

### Prerequisites

- Python 3.10+
- httpx
- BeautifulSoup4
- mcp-python-sdk
- typing-extensions

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/JackKuo666/PyPI-MCP-Server.git
   cd PyPI-MCP-Server
   ```

2. Install required dependencies:
   ```
   pip install -r requirements.txt
   ```

### Running the Server

```bash
python pypi_server.py
```

The server will communicate with MCP clients through standard input/output (stdio).

## 📚 MCP Tools

### Get Package Information
```python
get_package_info(package_name: str, version: Optional[str] = None) -> Dict
```
Get detailed information about a specified package, with optional version specification.

### Search Packages
```python
search_packages(query: str) -> List[Dict]
```
Search PyPI packages by keywords.

### Get Package Releases
```python
get_package_releases(package_name: str) -> Dict
```
Get all released version information for a specified package.

### Get Package Statistics
```python
get_package_stats(package_name: str) -> Dict
```
Get download statistics for a specified package.

## 🔧 Configuration

The server uses the MCP protocol to communicate with clients through standard input/output (stdio), no network port configuration needed.

## 📋 Integration with AI Assistants

### Using Claude Desktop

Add the following configuration to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "pypi": {
      "command": "python",
      "args": ["pypi_server.py"]
    }
  }
}
```

### Usage Examples

In your AI assistant, you can call the PyPI MCP tools as follows:

```
Use PyPI tool to search for Flask package:
@pypi search_packages("flask")

Get detailed information about a specific package:
@pypi get_package_info("requests")

Get information about a specific version of a package:
@pypi get_package_info("django", "4.2.0")

View all released versions of a package:
@pypi get_package_releases("numpy")

Get download statistics for a package:
@pypi get_package_stats("pandas")
```

## 📄 License

[MIT](LICENSE)
