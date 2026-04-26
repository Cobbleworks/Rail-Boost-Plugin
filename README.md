# Rail Boost

Part of the Cobbleworks Minecraft plugin ecosystem.

Source section copied from the main plugin collection repository:
https://github.com/BerndHagen/Minecraft-Server-Plugins

## Overview

A comprehensive minecart enhancement plugin that transforms vanilla minecart transportation into a powerful and customizable system. Each minecart can be individually configured with speed levels, automated item collection, built-in storage, and advanced physics improvements for reliable rail-based transportation networks.

### Core Features:
- **Speed Control:** 6 configurable speed levels (0.25x to 4.0x) with intelligent physics handling for curves and uphill sections
- **Auto-Pickup System:** Automatic item collection within configurable radius (1-5 blocks) with customizable blacklist filtering
- **Storage Integration:** Each minecart has its own 27-slot inventory accessible via GUI, with automatic item sorting
- **Advanced Physics:** Enhanced curve navigation, uphill momentum preservation, and anti-stuck mechanisms for smooth travel
- **Magnetism System:** Optional minecart-to-minecart attraction for train formation with intelligent collision prevention
- **Visual Effects:** Customizable particle trails with intensity scaling based on speed and multiple particle types
- **Performance Tools:** Real-time speedometer with BossBar display showing current velocity in km/h
- **Automation Features:** Auto-sit functionality for seamless boarding and chunkloading for uninterrupted long-distance travel
- **Persistent Configuration:** All settings are saved per-minecart and persist through server restarts

### Player Commands:
| Command | Description |
|---------|-------------|
| `/railboost speed <1-6>` | Sets speed level (0.25x to 4.0x multiplier) |
| `/railboost autopickup <true/false>` | Toggles automatic item collection |
| `/railboost autopickup radius <1-5>` | Sets pickup radius in blocks |
| `/railboost storage` | Opens minecart's dedicated inventory |
| `/railboost speedometer <true/false>` | Shows/hides real-time speed display |
| `/railboost chunkload <true/false>` | Enables chunk loading while traveling |
| `/railboost magnet <true/false>` | Toggles minecart magnetism for train formation |
| `/railboost effect <true/false>` | Enables particle trail effects |
| `/railboost effect type <particle>` | Sets particle type (FLAME, HEART, CLOUD, etc.) |
| `/railboost autosit <true/false>` | Automatic boarding when approaching minecart |
| `/railboost blacklist add/remove <item>` | Manages auto-pickup item filter |
| `/railboost blacklist list` | Shows current blacklisted items |
| `/railboost info` | Displays all current minecart settings |

**Note:** Most commands require sitting in an activated minecart. Use `/railboost info` to verify activation status.

**Aliases:** `/rb` – **Activation:** Automatic when using any command while in a minecart

## License

This project is licensed under the MIT License.