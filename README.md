# 🚀 Chrome Extension Boilerplate with React 18

<div align="center">
  <img src="src/assets/img/icon-128.png" width="128" alt="Extension Icon"/>
  
  [![npm version](https://img.shields.io/npm/v/chrome-extension-boilerplate-react?color=blue)](https://www.npmjs.com/package/chrome-extension-boilerplate-react)
  [![npm downloads](https://img.shields.io/npm/dw/chrome-extension-boilerplate-react?color=green)](https://www.npmjs.com/package/chrome-extension-boilerplate-react)
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
</div>

## ✨ Features

- ⚡️ **Modern Stack**: React 18, Webpack 5, TypeScript
- 🔥 **Hot Reload**: Instant feedback during development
- 📦 **Manifest V3**: Latest Chrome Extension architecture
- 🛠 **DevTools Support**: Built-in Chrome DevTools integration
- 🎨 **TypeScript**: Full TypeScript support with type definitions
- 🧰 **Development Tools**: ESLint, Prettier, and more

## 🚀 Quick Start

### Prerequisites
- Node.js >= 18
- npm or yarn
- Google Chrome browser

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/jacksonmillerdev/chrome-extension-boilerplate-react.git
   cd chrome-extension-boilerplate-react
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure your extension**
   - Update `package.json` with your extension details
   - Modify `src/manifest.json` with your extension name and settings

4. **Start development**
   ```bash
   npm start
   ```

5. **Load the extension in Chrome**
   - Open Chrome and go to `chrome://extensions/`
   - Enable "Developer mode"
   - Click "Load unpacked"
   - Select the `build` folder

## 📁 Project Structure

```
src/
├── assets/          # Static assets (images, fonts, etc.)
├── pages/           # Extension pages (popup, options, etc.)
├── background/      # Background scripts
├── content/         # Content scripts
└── manifest.json    # Extension manifest
```

## 🔧 Development

### Available Scripts

- `npm start` - Start development server with hot reload
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run format` - Format code with Prettier

### Hot Reloading

The boilerplate supports hot reloading for a better development experience. To use a custom port:

```bash
PORT=6002 npm start
```

### Content Scripts

To add content scripts, configure them in `webpack.config.js`:

```js
{
  entry: {
    myContentScript: "./src/js/myContentScript.js"
  },
  chromeExtensionBoilerplate: {
    notHotReload: ["myContentScript"]
  }
}
```

And in `manifest.json`:

```json
{
  "content_scripts": [
    {
      "matches": ["https://www.google.com/*"],
      "js": ["myContentScript.bundle.js"]
    }
  ]
}
```

## 🔐 Environment Variables

For API keys and sensitive data, use environment-specific secret files:

```js
// secrets.development.js
export default { 
  apiKey: 'your-dev-key' 
};

// In your code
import secrets from 'secrets';
```

## 📦 Building for Production

```bash
NODE_ENV=production npm run build
```

The `build` folder will contain your production-ready extension.

## 📚 Resources

- [Chrome Extension Documentation](https://developer.chrome.com/docs/extensions/)
- [Manifest V3 Migration Guide](https://developer.chrome.com/docs/extensions/mv3/intro/mv3-migration/)
- [Webpack Documentation](https://webpack.js.org/concepts/)
- [React Documentation](https://reactjs.org/docs/getting-started.html)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
