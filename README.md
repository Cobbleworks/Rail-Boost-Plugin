<p align="center">
  <img src="images/plugin-logo.png" alt="Rail Boost" width="128" />
</p>
<h1 align="center">Rail Boost</h1>
<p align="center">
  <b>A comprehensive minecart enhancement system for Minecraft servers.</b><br>
  <b>Speed control, auto-pickup, built-in storage, preset system, and advanced physics.</b>
</p>
<p align="center">
  <a href="https://github.com/Cobbleworks/Rail-Boost/releases"><img src="https://img.shields.io/github/v/release/Cobbleworks/Rail-Boost?include_prereleases&style=flat-square&color=4CAF50" alt="Latest Release"></a>&nbsp;&nbsp;<a href="https://github.com/Cobbleworks/Rail-Boost/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square" alt="License"></a>&nbsp;&nbsp;<img src="https://img.shields.io/badge/Java-17+-orange?style=flat-square" alt="Java Version">&nbsp;&nbsp;<img src="https://img.shields.io/badge/Minecraft-1.21+-green?style=flat-square" alt="Minecraft Version">&nbsp;&nbsp;<img src="https://img.shields.io/badge/Platform-Spigot%2FPaper-yellow?style=flat-square" alt="Platform">&nbsp;&nbsp;<img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square" alt="Status">
</p>

Rail Boost is an open-source Minecraft plugin that transforms vanilla minecart transportation into a powerful, fully configurable system. Each minecart can be individually configured with six speed levels, automated item collection, a 27-slot built-in storage inventory, and a preset system that lets players save and share minecart configurations using named sticks. The plugin also adds advanced physics improvements including intelligent curve navigation, uphill momentum preservation, and anti-stuck mechanisms so minecarts travel smoothly and reliably across even complex rail networks.

### **Core Features**

- **Speed Control:** Six configurable speed levels (0.25× to 4.0×) with intelligent physics handling for curves, uphill sections, and speed transitions
- **Auto-Pickup System:** Automatic item collection within a configurable radius (1–5 blocks) with per-cart blacklist filtering for precise control
- **Storage Integration:** Each minecart has its own dedicated 27-slot inventory accessible via a GUI, with automatic item sorting
- **Preset System:** Create, save, and share named minecart configurations using sticks — apply saved presets to any cart via right-click
- **Predefined Presets:** Three built-in standard presets for common use cases — Speed, Collector, and Magnet configurations
- **Advanced Physics:** Enhanced curve navigation, uphill momentum preservation, multi-block position checking, and anti-stuck mechanisms for smooth travel
- **Magnetism System:** Optional minecart-to-minecart attraction for forming train convoys with intelligent collision prevention
- **Visual Effects:** Customizable particle trails with intensity scaling based on speed and multiple particle type options
- **Real-Time Speedometer:** BossBar display showing current velocity in km/h with color-coded speed indicators
- **Chunk Loading:** Automatic chunk force-loading with timed unloading to ensure smooth travel across unloaded areas
- **F-Key Access:** Open storage and hopper inventories while seated in a minecart using the F key
- **Persistent Configuration:** All per-cart settings and preset data are saved to YAML and persist across server restarts

### **Supported Platforms**

- **Server Software:** `Spigot`, `Paper`, `Purpur`, `CraftBukkit`
- **Minecraft Versions:** `1.21.5`, `1.21.6`, `1.21.7`, `1.21.8`, `1.21.9`, `1.21.10` and higher
- **Java Requirements:** `Java 17+`

### **Installation**

1. Download the latest `.jar` from the [Releases](https://github.com/Cobbleworks/Rail-Boost/releases) page
2. Stop your Minecraft server
3. Copy the `.jar` into your server's `plugins` folder
4. Start your server — a default configuration folder is generated at `plugins/RailBoost/`

### **Player Commands**

| Command | Description |
|---------|-------------|
| `/railboost speed <1-6>` | Set the current minecart's speed level (0.25× to 4.0× multiplier) |
| `/railboost autopickup <true/false>` | Toggle automatic item collection for the current minecart |
| `/railboost autopickup radius <1-5>` | Set the item pickup radius in blocks |
| `/railboost storage` | Open the current minecart's dedicated 27-slot inventory |
| `/railboost speedometer <true/false>` | Show or hide the real-time BossBar speed display |
| `/railboost chunkload <true/false>` | Enable or disable automatic chunk loading while traveling |
| `/railboost magnet <true/false>` | Toggle minecart-to-minecart magnetism for train formation |
| `/railboost effect <true/false>` | Enable or disable particle trail effects |
| `/railboost effect type <particle>` | Set the particle type (e.g., `FLAME`, `HEART`, `CLOUD`) |
| `/railboost blacklist add/remove <item>` | Add or remove an item from the auto-pickup filter |
| `/railboost blacklist list` | Display all currently blacklisted items |
| `/railboost info` | Display all current settings for the active minecart |

**Aliases:** `/rb`

**Note:** Most commands require the player to be seated in an active (configured) minecart. Use `/railboost info` to verify activation status.

### **License**

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

