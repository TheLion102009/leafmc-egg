# 🍃 LeafMC Pterodactyl/Pelican Egg

A fully optimized Pterodactyl/Pelican egg for **LeafMC** servers with automatic version detection and performance-tuned JVM flags.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Pterodactyl](https://img.shields.io/badge/Pterodactyl-Compatible-green.svg)](https://pterodactyl.io)
[![Pelican](https://img.shields.io/badge/Pelican-Compatible-brightgreen.svg)](https://pelican.dev)

## ✨ Features

- 🔄 **Automatic Latest Builds** - Always get the newest LeafMC build
- 🎯 **Version Selection** - Support for Minecraft 1.21.4 through 1.21.8
- ⚡ **Optimized JVM Flags** - Pre-configured for maximum performance
- 🛡️ **Smart Fallback** - Automatic fallback if API is unavailable
- 📦 **Easy Installation** - One-click server setup
- 🔧 **Fully Configurable** - All settings adjustable via panel

## 🚀 Supported Versions

- Minecraft 1.21.4
- Minecraft 1.21.5
- Minecraft 1.21.6
- Minecraft 1.21.7
- Minecraft 1.21.8 (Default)

## 📥 Installation

### Method 1: Direct Import (Recommended)

1. Download the `egg-leaf-m-c.json` file
2. Navigate to your **Admin Panel** → **Nests**
3. Select your **Minecraft** nest
4. Click **Import Egg**
5. Upload the JSON file
6. Done! 🎉

### Method 2: Raw Import

```bash
cd /var/www/pterodactyl
php artisan p:egg:import egg-leaf-m-c.json
```

## ⚙️ Configuration

### Server Variables

| Variable | Description | Default | Options |
|----------|-------------|---------|---------|
| **Minecraft Version** | Target Minecraft version | `1.21.8` | 1.21.4 - 1.21.8 |
| **Build Number** | Specific build or latest | `latest` | `latest` or build number |
| **Server Jar File** | Name of the server jar | `server.jar` | Any `.jar` filename |

### JVM Optimization

The egg comes pre-configured with optimized JVM flags for Minecraft servers:

```bash
-Xms512M 
-Xmx{{SERVER_MEMORY}}M 
-XX:+UseG1GC 
-XX:+ParallelRefProcEnabled 
-XX:MaxGCPauseMillis=200 
-XX:+UnlockExperimentalVMOptions 
-XX:+AlwaysPreTouch 
-XX:+DisableExplicitGC 
-XX:+PerfDisableSharedMem 
-XX:G1NewSizePercent=30 
-XX:G1MaxNewSizePercent=40 
-XX:G1HeapRegionSize=16M 
-XX:G1ReservePercent=20 
-XX:InitiatingHeapOccupancyPercent=15
```

**Performance Benefits:**
- ⚡ Reduced lag spikes through G1GC
- 🎯 Optimized garbage collection timing
- 💾 Better memory management
- 🔥 Improved tick performance

## 📋 Requirements

- **Panel**: Pterodactyl v1.x or Pelican v1.x
- **Docker Image**: `ghcr.io/pterodactyl/yolks:java_21`
- **Java**: Java 21 (included in Docker image)
- **RAM**: Minimum 2GB, recommended 4GB+

## 🔧 Usage

### Creating a Server

1. Go to your Panel and create a new server
2. Select the **LeafMC** egg
3. Configure your desired settings:
   - Set Minecraft version (e.g., `1.21.8`)
   - Choose build number or leave as `latest`
   - Allocate memory (minimum 2048MB recommended)
4. Start the server

### Updating the Server

To update to a new build:

1. Stop your server
2. Click **Reinstall** in the panel
3. The latest build will be downloaded automatically
4. Start your server

Or manually specify a build number in the server variables.

## 🐛 Troubleshooting

### Server won't start

**Check logs for errors:**
```bash
# Common issues:
- Insufficient memory allocated
- Port already in use
- Java version mismatch
```

### Download fails

The egg includes automatic fallback mechanisms:
- First tries specified version/build
- Falls back to latest stable build
- Uses hardcoded stable version as last resort

### Can't find specific version

Check available versions at: `https://api.leafmc.one/v2/projects/leaf`

## 🤝 Contributing

Contributions are welcome! Feel free to:

- 🐛 Report bugs
- 💡 Suggest features
- 🔧 Submit pull requests
- 📖 Improve documentation

## 📝 License

This egg configuration is released under the MIT License.

## 🔗 Links

- [LeafMC Official](https://leafmc.one)
- [LeafMC API](https://api.leafmc.one)
- [Pterodactyl Panel](https://pterodactyl.io)
- [Pelican Panel](https://pelican.dev)

## ⭐ Credits

- **Created by**: TheLion102009
- **LeafMC**: LeafMC Development Team
- **Based on**: Pterodactyl/Pelican Egg Format

---

<div align="center">

**Made with ❤️ for the Minecraft community**

If this helped you, consider giving it a ⭐!

</div>
