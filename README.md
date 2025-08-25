# Perlink

A powerful browser chooser application that allows you to select which browser to open URLs with on a per-link basis.

Tested to work on:
- ✔️ Manjaro XFCE (Linux, based on Arch)
- ✔️ Windows 11
- ✔️ macOS (Intel/Apple Silicon)

## ✨ Features

- **🎯 Smart Browser Selection**: Choose which browser to open any URL with
- **🔗 URL Expansion**: Automatically expand shortened URLs using configurable services
- **📋 Clipboard Integration**: Automatically detect URLs from your clipboard
- **🪟 Window Title Detection**: Extract URLs from browser window titles
- **🌐 Protocol Handler**: Set as default browser for seamless integration
- **🎨 Modern UI**: Clean, centered interface with large, accessible buttons
- **⚙️ Configurable**: Add/remove browsers with simple commands
- **🔧 Cross-platform**: Works on Linux, Windows, and macOS

## 🚀 Quick Start

1. **Download** the executable from the [releases page](https://github.com/visnkmr/perlink/releases)
2. **Set as default browser** (optional) for seamless integration
3. **Run** the application to start choosing browsers!

## 📋 Command Line Options

Perlink supports various command-line options for configuration and automation:

### Basic Usage
```bash
# Launch GUI application
./perlink

# Open with specific URL
./perlink "https://www.example.com"

# Open with shortened URL (will auto-expand)
./perlink "https://bit.ly/3abc123"
```

### Configuration Commands

#### Reinitialize Browser List
```bash
./perlink reinit
```
Clears all saved browser preferences and re-detects installed browsers automatically.

#### Add Custom Browser
```bash
./perlink add "My Browser" "/path/to/browser --incognito %s"
```
- First argument: Display name for the browser
- Second argument: Command to execute (use `%s` as URL placeholder)

#### Remove All Browsers
```bash
./perlink clear
```
Clears the entire browser list. Use `reinit` afterward to auto-detect browsers.

#### Windows Protocol Handler
```bash
# Install as system browser
./perlink install

# Remove protocol handler
./perlink uninstall
```

### Examples

```bash
# Add Firefox with private browsing
./perlink add "Firefox Private" "firefox --private-window %s"

# Add Chrome with incognito mode
./perlink add "Chrome Incognito" "google-chrome --incognito %s"

# Add custom browser with specific profile
./perlink add "Work Firefox" "firefox -P work %s"
```

## 🎨 User Interface

The application features a traditional boxy interface with:

- **Keyboard shortcuts**:
  - `Q`: Quit application
  - `F`: Toggle fullscreen (FLTK version)

## ⚙️ Configuration

### Browser Storage Location
- **Linux**: `~/.config/perlink/`
- **Windows**: `C:\Users\<username>\AppData\Roaming\perlink\`
- **macOS**: `~/Library/Application Support/perlink/`

### Configuration Files
Each browser is stored as a text file with the browser name:
- `Firefox.txt` → contains: `firefox %s`
- `Chrome.txt` → contains: `google-chrome %s`
- `Custom Browser.txt` → contains: `/path/to/custom/browser %s`

### URL Expansion Service
Configure the URL expansion service in the config folder:
```bash
# Default service
website.su = https://unshorten.me/s/
```

## 🔧 Development

Built with:
- 🦀 **Rust** - Fast, safe systems programming
- 🎨 **fltk** - GUI framework

### Building from Source

```bash
# Clone the repository
git clone https://github.com/visnkmr/perlink.git
cd perlink

# Build release version
cargo build --release

# Run
cargo run
```

## 📖 Usage Examples

### For Web Developers
1. **Cross-browser testing**: Open links in all browsers simultaneously
2. **Debugging**: Compare rendering across different browsers
3. **Responsive testing**: Quickly switch between browsers

### For Regular Users
1. **Privacy browsing**: Use different browsers for different purposes
2. **Work/personal separation**: Dedicated browsers for work vs personal use
3. **Extension-free browsing**: Use secondary browsers without extensions

### For Productivity
1. **URL management**: Quickly choose how to open various types of links
2. **Research workflows**: Different browsers for different research tasks
3. **Content creation**: Preview content in multiple browsers

## 🐛 Troubleshooting

### Common Issues

**"No browsers detected"**
```bash
./perlink reinit
```

**"Protocol handler not working" (Windows)**
```bash
./perlink uninstall
./perlink install
```

**"URL not expanding"**
- Check your internet connection
- Verify the URL expansion service is configured correctly

### Logs and Debugging
The application generates detailed logs for troubleshooting. Check the application data directory for log files.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## 📄 License

See LICENSE.md for details.

---

*Made with ❤️ for developers and power users who need precise control over their browsing experience.*

|Browser-name| command|
|-|-|
|Firefox| firefox|
|Vivaldi Stable | vivaldi-stable|
|Chromium| chromium|
|Firefox beta|firefox-beta|
|Firefox dev|firefox-dev|

Config files now stored @ 
```
Linux: /home/<username>/.config/perlink/
Windows: Drive:\Users\username\AppData\Roaming\perlink\
```  
