# CheckMate Browser Extension

A browser extension that adds fact-checking capabilities to news websites and social media platforms by integrating with the CheckMate analysis service.

## 🔍 Overview

CheckMate is a browser extension designed to help users fact-check content across various news websites and social media platforms. The extension adds a convenient floating button to whitelisted sites, allowing users to quickly analyze articles and posts for credibility.

## ✨ Features

### 🌐 Multi-Platform Support

- **News Websites**: Works on major Malaysian and international news sites
- **Social Media**: Special integration with TikTok for video content analysis
- **Article Platforms**: Supports Medium, Substack, and other publishing platforms

### 🎯 Smart Site Detection

- **Whitelist Management**: Automatically appears on trusted news sources
- **Blocklist Control**: Right-click context menu to enable/disable per site
- **Dynamic Loading**: Intelligent detection of content types and site structures

### 🔘 User Interface

- **Floating Button**: Unobtrusive circular button with CheckMate icon
- **Hover Effects**: Smooth animations and visual feedback
- **Responsive Design**: Adapts to different screen sizes and layouts

### 📱 TikTok Integration

- **Video Analysis**: Extracts TikTok video URLs for fact-checking
- **Smart Positioning**: Adapts button placement for feed vs. individual video pages
- **Direct URL Support**: Works with both embedded and direct TikTok links

## 🗂️ Supported Sites

### Malaysian News Sources

- The Star (thestar.com.my)
- New Straits Times (nst.com.my)
- Malay Mail (malaymail.com)
- Free Malaysia Today (freemalaysiatoday.com)
- MalaysiaNow (malaysianow.com)
- Malaysiakini (malaysiakini.com)
- Astro Awani (astroawani.com)
- Bernama (bernama.com)
- The Edge Markets (theedgemarkets.com)
- The Malaysian Insight (themalaysianinsight.com)

### International News Sources

- BBC (bbc.com)
- CNN (cnn.com)
- Reuters (reuters.com)
- Associated Press (ap.org)
- The Guardian (theguardian.com)
- Al Jazeera (aljazeera.com)
- Channel News Asia (channelnewsasia.com)
- The Straits Times (straitstimes.com)

### Social Media & Platforms

- X/Twitter (x.com)
- TikTok (tiktok.com)
- Medium (medium.com)
- Substack (substack.com)

## 🚀 Installation

### Prerequisites

- Chrome, Edge, or other Chromium-based browser
- CheckMate analysis service running on `localhost:3000`

### Steps

1. **Download the Extension**

   ```bash
   git clone https://github.com/your-repo/checkmate-browser-extension.git
   cd checkmate-browser-extension
   ```

2. **Load in Browser**

   - Open Chrome and navigate to `chrome://extensions/`
   - Enable "Developer mode" in the top right
   - Click "Load unpacked" and select the extension directory

3. **Verify Installation**
   - Visit any supported news website
   - Look for the CheckMate floating button on the right side of the page

## 🎮 Usage

### Basic Operation

1. **Navigate** to any supported news website or TikTok
2. **Look** for the floating CheckMate button (circular with search-check icon)
3. **Click** the button to analyze the current page/content
4. **Review** results in the CheckMate analysis interface

### Site Management

- **Enable/Disable**: Right-click on any page → "Toggle CheckMate Button for this site"
- **Notifications**: Visual feedback confirms when sites are added/removed from blocklist

### TikTok Specific

- **Feed Pages**: Button appears next to navigation controls
- **Video Pages**: Button positioned near the next video arrow
- **Analysis**: Extracts video URLs automatically for fact-checking

## 🛠️ Development

### File Structure

```
checkmate-browser-extension/
├── manifest.json          # Extension configuration
├── background.js          # Service worker for context menus
├── generic-content.js     # Main content script for news sites
├── tiktok-content.js      # TikTok-specific content script
├── style.css             # Additional styling
└── README.md             # This file
```

### Key Components

#### Content Scripts

- **generic-content.js**: Handles whitelist management and button injection for news sites
- **tiktok-content.js**: Specialized TikTok integration with URL extraction

#### Background Script

- **background.js**: Manages context menus and cross-tab communication

#### Storage Management

```javascript
// Access whitelist management
window.checkmate.addToWhitelist("example.com");
window.checkmate.removeFromWhitelist("example.com");
window.checkmate.getWhitelist();
```

## ⚙️ Configuration

### Storage Structure

```javascript
{
  "checkmate-whitelist": ["site1.com", "site2.com", ...],
  "checkmate-blocklist": ["blocked-site.com", ...]
}
```

### Customization

- Modify `defaultWhitelist` in `generic-content.js` to add new sites
- Adjust button positioning by editing CSS styles
- Configure CheckMate service URL (default: `localhost:3000`)

## 🔒 Permissions

- **activeTab**: Access current tab content for analysis
- **storage**: Save whitelist and blocklist preferences
- **contextMenus**: Right-click menu for site management

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test on multiple sites
5. Submit a pull request

## 📄 License

[License information here]

## 🆘 Support

For issues or feature requests, please [create an issue](https://github.com/your-repo/checkmate-browser-extension/issues) in the GitHub repository.

---

**Note**: This extension requires the CheckMate analysis service to be running locally on port 3000. Ensure the service is active before using the extension.
