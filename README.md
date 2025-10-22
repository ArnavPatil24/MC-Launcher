# Minecraft Launcher - Native Qt C++ Edition

A modern, native Minecraft launcher built with Qt C++ for optimal performance and native Windows integration.

## Features

✨ **Native Performance** - Built with Qt C++ for fast startup and minimal resource usage  
🎮 **Multiple Instances** - Create and manage multiple Minecraft installations  
🔧 **Mod Loader Support** - Fabric, Forge, and Quilt support  
📦 **File Integrity Checker** - Automatically detects and repairs missing files  
🌙 **Dark Theme** - Modern, beautiful dark UI  
📴 **Offline Mode** - Play Minecraft without authentication (default enabled)  
💾 **Local Storage** - All data stored locally in JSON files (no database required)


## Project Structure

```
MinecraftLauncher-Qt/
├── src/                          # C++ source files
│   ├── main.cpp                  # Application entry point
│   ├── loginwindow.cpp/h         # Login screen
│   ├── mainwindow.cpp/h          # Main dashboard
│   ├── instance_manager.cpp/h   # Instance management
│   ├── file_checker.cpp/h        # File integrity checker
│   ├── mod_loader.cpp/h          # Mod loader support
│   ├── settings.cpp/h            # Settings management
│   ├── create_instance_dialog.cpp/h
│   ├── instance_settings_dialog.cpp/h
│   └── utils/
│       ├── json_handler.cpp/h    # JSON file operations
│       ├── download_manager.cpp/h # File downloads
│       └── minecraft_launcher.cpp/h # Minecraft launcher logic
│
├── ui/                           # Qt Designer UI files
│   ├── loginwindow.ui
│   ├── mainwindow.ui
│   ├── create_instance_dialog.ui
│   ├── instance_settings_dialog.ui
│   └── about.ui
│
├── data/                         # Data files
│   ├── launcher_config.json      # Launcher configuration
│   ├── user_data.json            # User preferences
│   └── instances/                # Minecraft instances
│
├── assets/                       # Resources
│   ├── icons/
│   ├── themes/
│   └── images/
│
├── installer/                    # Installer scripts
│   └── setup.nsi                 # NSIS installer script
│
├── CMakeLists.txt                # Build configuration
└── README.md                     # This file
```


## Configuration

### launcher_config.json

Located at: `%APPDATA%/MinecraftLauncher/launcher_config.json`

```json
{
  "default_instance_path": "instances/",
  "theme": "dark",
  "offline_mode": true,
  "java_path": "C:/Program Files/Java/jre-17/bin/java.exe",
  "default_memory_mb": 2048,
  "default_jvm_args": "-Xmx2G -Xms512M"
}
```

### user_data.json

Stores the last logged-in username for auto-fill.

```json
{
  "username": "Player",
  "last_login": "2024-01-20T10:30:00Z"
}
```

## Instance Structure

Each instance has its own folder with:

```
instances/my-instance/
├── instance.json         # Instance configuration
├── mods/                 # Mod files (.jar)
├── saves/                # World saves
├── config/               # Mod configurations
├── resourcepacks/        # Resource packs
├── shaderpacks/          # Shader packs
└── screenshots/          # Screenshots
```

## 📦 Downloads & Installation

### Official Releases
Download the latest version from GitHub:
- **Releases:** https://github.com/ArnavPatil24/MC-Launcher/releases
- **Latest:** https://github.com/ArnavPatil24/MC-Launcher/releases/latest

1. Download `MinecraftLauncher_Setup_1.0.0.exe`
2. Run the installer
3. Launch from desktop shortcut

### System Requirements
- **OS:** Windows 10/11 (64-bit)
- **RAM:** 4GB minimum, 8GB recommended
- **Storage:** 2GB free space
- **Network:** Internet connection for downloads
- **Graphics:** OpenGL 3.0+ compatible

---

## 🎯 Quick Start

1. **Launch** the application
2. **Create Instance** - Click "Create Instance" button
3. **Select Version** - Choose any Minecraft version (1.0 to latest)
4. **Configure** - Set memory, Java path, mod loader
5. **Play** - Click play and enjoy!

---

## ✨ What's New (v1.0.0)

### Network & Connectivity
- ✅ **Fixed "No TLS backend" error** - Complete OpenSSL integration
- ✅ **Real network status** - Shows "Online" when connected
- ✅ **Complete version loading** - All 90+ Minecraft versions available
- ✅ **Secure downloads** - HTTPS with TLS encryption

### Performance & Reliability
- ✅ **All dependencies included** - Complete Qt plugin set
- ✅ **Archive extraction** - 7-Zip integration working
- ✅ **Image loading** - All formats supported (PNG, JPG, SVG, etc.)
- ✅ **Professional installer** - All required files bundled

### User Experience
- ✅ **Modern dark theme** - Beautiful, consistent UI
- ✅ **Complete version support** - From 1.0 (2009) to latest
- ✅ **Mod loader support** - Fabric, Forge, and Quilt
- ✅ **Instance management** - Multiple game installations
- ✅ **File integrity checking** - Automatic repair features

## Troubleshooting

### Java Not Found

**Problem**: "Java installation verification failed"

**Solutions**:
1. Install Java 17+ from https://adoptium.net/
2. Set `JAVA_HOME` environment variable
3. Manually specify Java path in instance settings

### Qt DLLs Missing

**Problem**: Application won't start, missing Qt6*.dll

**Solution**: Use `windeployqt`:
```powershell
windeployqt.exe MinecraftLauncher.exe
```

### Build Errors

**Problem**: CMake can't find Qt

**Solution**: Set `CMAKE_PREFIX_PATH`:
powershell
cmake .. -DCMAKE_PREFIX_PATH="C:/Qt/6.x.x/msvc2019_64"


## Development

### Code Style

- Follow Qt coding conventions
- Use camelCase for variables and functions
- Use PascalCase for classes
- Comment complex logic
- Keep functions focused and small

### Adding Features

1. Add header declaration in appropriate `.h` file
2. Implement in corresponding `.cpp` file
3. Update UI files if needed using Qt Designer
4. Test thoroughly before committing

### Testing

powershell
# Manual testing
cmake --build . --config Debug
.\Debug\MinecraftLauncher.exe

# Check for memory leaks with valgrind (Linux)
valgrind --leak-check=full ./MinecraftLauncher



## License

This project is for educational purposes. Minecraft is a trademark of Mojang Studios.

## Credits

- **Qt Framework** - https://www.qt.io/
- **Minecraft** - Mojang Studios
- **Icons** - Emoji/Unicode

## Support

For issues and questions:
1. Check the Troubleshooting section
2. Check Minecraft launcher documentation

---

**Built with ❤️ using Qt C++**
