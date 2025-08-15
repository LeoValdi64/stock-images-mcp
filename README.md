# Stock Images MCP Server

A Model Context Protocol (MCP) server for searching and downloading stock images from multiple platforms including Pexels, Unsplash, and Pixabay.

## Features

- 🔍 **Multi-platform search**: Search across Pexels, Unsplash, and Pixabay simultaneously
- 📥 **Automatic downloads**: Download images directly to your local machine
- 🎯 **Flexible queries**: Search by keywords with customizable results
- 🔑 **API key management**: Easy configuration with environment variables
- 📁 **Organized downloads**: Images are saved to a dedicated downloads folder

## Supported Platforms

- **Pexels**: High-quality free stock photos
- **Unsplash**: Beautiful free images and photos
- **Pixabay**: Stunning free images and royalty free stock photos

## Installation

1. **Clone or download this repository**

   ```bash
   git clone <repository-url>
   cd stock-images-mcp
   ```

2. **Create a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install mcp requests python-dotenv
   ```

4. **Set up API keys**

   ```bash
   cp .env.example .env
   ```

   Edit the `.env` file and add your API keys:

   - **Pexels**: Get your API key from [https://www.pexels.com/api/](https://www.pexels.com/api/)
   - **Unsplash**: Get your API key from [https://unsplash.com/developers](https://unsplash.com/developers)
   - **Pixabay**: Get your API key from [https://pixabay.com/api/docs/](https://pixabay.com/api/docs/)

## Usage

### Running the Server

```bash
# Run the server directly
python server.py

# Or test with MCP CLI (recommended for development)
mcp dev server.py
```

### Available Tools

The MCP server provides three main tools:

#### 1. `search_stock_images`

Search for stock images across multiple platforms.

**Parameters:**

- `query` (required): Search term for images
- `platform` (optional): Platform to search on (`all`, `pexels`, `unsplash`, `pixabay`). Default: `all`
- `per_page` (optional): Number of images per platform (1-50). Default: `10`

**Example:**

```json
{
  "query": "nature landscape",
  "platform": "all",
  "per_page": 15
}
```

#### 2. `download_stock_image`

Download a specific image by URL.

**Parameters:**

- `image_url` (required): URL of the image to download
- `filename` (optional): Custom filename for the downloaded image

**Example:**

```json
{
  "image_url": "https://images.pexels.com/photos/123456/pexels-photo-123456.jpeg",
  "filename": "my_nature_photo.jpg"
}
```

#### 3. `search_and_download_images`

Search for images and automatically download them.

**Parameters:**

- `query` (required): Search term for images
- `platform` (optional): Platform to search on (`all`, `pexels`, `unsplash`, `pixabay`). Default: `all`
- `num_images` (optional): Number of images to download (1-20). Default: `5`

**Example:**

```json
{
  "query": "business meeting",
  "platform": "unsplash",
  "num_images": 10
}
```

## File Structure

```
stock-images-mcp/
├── server.py          # Main MCP server implementation
├── .env.example       # Template for environment variables
├── .env              # Your actual API keys (create this)
├── downloads/        # Downloaded images (created automatically)
├── venv/            # Virtual environment
└── README.md        # This file
```

## API Key Setup

### Pexels API

1. Go to [https://www.pexels.com/api/](https://www.pexels.com/api/)
2. Sign up for a free account
3. Get your API key from the dashboard
4. Add it to your `.env` file as `PEXELS_API_KEY=your_key_here`

### Unsplash API

1. Go to [https://unsplash.com/developers](https://unsplash.com/developers)
2. Create a developer account
3. Create a new application
4. Get your Access Key
5. Add it to your `.env` file as `UNSPLASH_API_KEY=your_key_here`

### Pixabay API

1. Go to [https://pixabay.com/api/docs/](https://pixabay.com/api/docs/)
2. Sign up for a free account
3. Get your API key
4. Add it to your `.env` file as `PIXABAY_API_KEY=your_key_here`

## Error Handling

The server includes comprehensive error handling:

- Missing API keys are detected and reported
- Network errors are caught and displayed
- Invalid URLs are handled gracefully
- Download failures are logged

## Development

### Testing the Server

You can test the server using the MCP CLI:

```bash
# Install MCP CLI if you haven't already
pip install mcp[cli]

# Test the server
mcp dev server.py
```

### Adding New Platforms

To add support for additional stock image platforms:

1. Add the API key to the environment variables
2. Create a search function similar to `search_pexels()`
3. Add the platform to the tool handlers
4. Update the documentation

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

If you encounter any issues or have questions, please open an issue on the repository.
