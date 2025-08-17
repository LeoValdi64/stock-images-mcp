# Stock Images MCP Server

A Model Context Protocol (MCP) server for searching and downloading stock images from multiple platforms. Built for personal use with Cursor and shared with the community.

## 🚀 Quick Setup for Cursor

### Step 1: Add to Cursor's MCP Configuration

Add this configuration to your `~/.cursor/mcp.json` file:

```json
{
  "mcpServers": {
    "stock-images-mcp": {
      "command": "uvx",
      "args": ["git+https://github.com/Zulelee/stock-images-mcp"],
      "env": {
        "UNSPLASH_API_KEY": "your_unsplash_api_key_here",
        "PEXELS_API_KEY": "your_pexels_api_key_here",
        "PIXABAY_API_KEY": "your_pixabay_api_key_here"
      }
    }
  }
}
```

### Step 2: Get API Keys (Optional but Recommended)

**Unsplash:**
1. Go to https://unsplash.com/developers
2. Make sure you are logged in
3. Create an app
4. Get your API key from the app dashboard

**Pexels:**
1. Go to https://www.pexels.com/api/
2. Make sure you are logged in
3. Click "Your API Key" button
4. Copy your API key

**Pixabay:**
1. Go to https://pixabay.com/api/docs/
2. Make sure you are logged in
3. Find your API key under "Parameters" in the docs

### Step 3: Restart Cursor

After adding the configuration, restart Cursor to load the new MCP server.

### Step 4: Use the Tools

Once Cursor restarts, you can use the stock images tools directly in your conversations:

- Search for images: "Find tech workspace images"
- Download images: "Download 5 nature photos"
- Search specific platforms: "Search Unsplash for coding setup images"

## Available Tools

- **`search_stock_images`**: Search across Pexels, Unsplash, and Pixabay
- **`download_stock_image`**: Download a specific image by URL
- **`search_and_download_images`**: Search and automatically download images

## Supported Platforms

- **Pexels**: High-quality free stock photos
- **Unsplash**: Beautiful free images and photos  
- **Pixabay**: Stunning free images and royalty free stock photos
