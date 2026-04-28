<p align="center">
  <img src="images/plugin-logo.png" alt="Rail Boost Plugin" width="180" />
</p>
<h1 align="center">Rail Boost Plugin</h1>
<p align="center">
  <b>A comprehensive minecart enhancement system for Minecraft servers.</b><br>
  <b>Speed control, auto-pickup, built-in storage, preset system, and advanced physics.</b>
</p>
<p align="center">
  <a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/releases"><img src="https://img.shields.io/github/v/release/Cobbleworks/Rail-Boost-Plugin?include_prereleases&style=flat-square&color=4CAF50" alt="Latest Release"></a>&nbsp;&nbsp;<a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square" alt="License"></a>&nbsp;&nbsp;<img src="https://img.shields.io/badge/Java-17+-orange?style=flat-square" alt="Java Version">&nbsp;&nbsp;<img src="https://img.shields.io/badge/Minecraft-1.16+-green?style=flat-square" alt="Minecraft Version">&nbsp;&nbsp;<img src="https://img.shields.io/badge/Platform-Spigot%2FPaper-yellow?style=flat-square" alt="Platform">&nbsp;&nbsp;<img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square" alt="Status">&nbsp;&nbsp;<a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/issues"><img src="https://img.shields.io/github/issues/Cobbleworks/Rail-Boost-Plugin?style=flat-square&color=orange" alt="Open Issues"></a>
</p>

Rail Boost is an open-source Minecraft plugin that transforms vanilla minecart transportation into a fully configurable, preset-driven system. Each minecart can be configured with six speed levels, automated item collection, optional particle and magnet effects, chunk loading behavior, and shared preset storage managed through named preset sticks. The plugin also adds rail safety checks and speed handling so minecarts travel more reliably across complex track networks.

### **Core Features**

- **Speed Control:** Six configurable speed levels (0.25x to 4.0x) with intelligent physics handling for curves, uphill sections, and speed transitions
- **Auto-Pickup System:** Automatic item collection within a configurable radius (1-5 blocks) with per-cart blacklist filtering for precise control
- **Preset-Linked Shared Storage:** Minecarts with presets use shared preset storage inventories (54 slots) that can be opened and managed via commands
- **Preset System:** Create, save, and share named minecart configurations using sticks - apply saved presets to any cart via right-click
- **Predefined Presets:** Three built-in standard presets for common use cases - Speed, Collector, and Magnet configurations
- **Advanced Physics:** Enhanced curve navigation, uphill momentum preservation, multi-block position checking, and anti-stuck mechanisms for smooth travel
- **Magnetism System:** Optional minecart-to-minecart attraction for forming train convoys with intelligent collision prevention
- **Visual Effects:** Customizable particle trails with intensity scaling based on speed and multiple particle type options
- **Real-Time Speedometer:** BossBar display showing current velocity in km/h with color-coded speed indicators
- **Chunk Loading:** Automatic chunk force-loading with timed unloading to ensure smooth travel across unloaded areas
- **F-Key Access:** Open storage and hopper inventories while seated in a minecart using the F key
- **Persistent Configuration:** All per-cart settings and preset data are saved to YAML and persist across server restarts

### **Supported Platforms**

- **Server Software:** `Spigot`, `Paper`, `Purpur`, `CraftBukkit`
- **Minecraft Versions:** `1.16` and higher
- **Java Requirements:** `Java 17+`
- **Dependencies:** None - fully self-contained, no external plugins required

## **Table of Contents**

1. [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation Steps](#installation-steps)
    - [First Launch & Configuration](#first-launch--configuration)
    - [Verifying Installation](#verifying-installation)
2. [Configuration](#configuration)
    - [Preset Edit Settings](#preset-edit-settings)
    - [Data Storage](#data-storage)
3. [How It Works](#how-it-works)
4. [Commands](#commands)
    - [Command Reference](#command-reference)
5. [Permissions](#permissions)
6. [Building from Source](#building-from-source)
7. [License](#license)
8. [Screenshots](#screenshots)

## **Getting Started**

### **Prerequisites**

Before installing Rail Boost, confirm the following requirements are met:

- A Minecraft server running **Spigot**, **Paper**, **Purpur**, or any compatible fork
- Server version **1.16 or higher** (`api-version: 1.16` is the minimum)
- **Java 17** or newer installed on the machine running the server
- Operator or console access to install plugin files

No additional plugins or libraries are needed. Rail Boost has zero external dependencies.

### **Installation Steps**

1. Download the latest `RailBoost-x.x.x.jar` from the [Releases](https://github.com/Cobbleworks/Rail-Boost-Plugin/releases) page
2. **Stop your server completely** before placing any files
3. Copy the `.jar` into your server's `plugins/` directory
4. Start the server - Rail Boost generates its configuration folder automatically on first boot

### **First Launch & Configuration**

On the first server start after installation, Rail Boost creates the following structure:

```
plugins/
└── RailBoost/
    └── presets.yml   - All preset definitions including three built-in defaults
```

Three default presets are created automatically: `speed`, `collector`, and `magnet`. Get a preset stick with `/railboost preset <name>` and right-click any minecart to apply settings. Edit presets at any time using `/railboost edit`.

### **Verifying Installation**

- Run `/plugins` in-game - `RailBoost` should appear green in the list
- Run `/railboost list` to confirm the three default presets are loaded
- Run `/railboost preset speed` to get a Speed preset stick, then right-click a minecart - ride it and the BossBar speedometer should appear
- If the plugin fails to load, check the server console for `RailBoost` error messages (common causes: wrong Java version, corrupt JAR, or unsupported API version)

## **Configuration**

### **Preset Edit Settings**

Use `/railboost edit <preset> <setting> <value>` with these options:

| Setting | Value | Description |
|---------|-------|-------------|
| `speed` | `1..6` | Speed level (1 = Slow, 6 = Ultra Fast) |
| `autopickup` | `true/false` | Toggle item auto-pickup |
| `radius` | `1..5` | Auto-pickup radius in blocks |
| `speedometer` | `true/false` | Toggle BossBar speedometer display |
| `chunkload` | `true/false` | Toggle temporary force-loading of traversed chunks |
| `magnet` | `true/false` | Toggle minecart magnetism behavior |
| `effects` | `true/false` | Toggle particle trail effects |
| `effecttype` | Bukkit particle name | Set particle type (e.g. `FLAME`, `END_ROD`) |
| `blacklist` | `add/remove <material>` | Add or remove a material from the auto-pickup blacklist |
| `storage` | *(none)* | Open shared storage GUI for this preset |

### **Data Storage**

Rail Boost stores all preset definitions in `plugins/RailBoost/presets.yml`.

Each preset entry contains:

| Key | Type | Description |
|-----|------|-------------|
| `name` | string | Display name of the preset |
| `speed` | int | Speed level 1..6 |
| `autopickup` | boolean | Auto-pickup enabled flag |
| `pickupRadius` | int | Pickup radius 1..5 |
| `speedometer` | boolean | BossBar speed display flag |
| `chunkload` | boolean | Chunk loading flag |
| `magnet` | boolean | Magnet mode flag |
| `effects` | boolean | Particle effects flag |
| `effectType` | string | Bukkit particle type name |
| `blacklist` | list | Material names blocked from auto-pickup |

Default presets created by the plugin:

| Preset | Defaults |
|--------|----------|
| `speed` | `speed=4`, `speedometer=true` |
| `collector` | `autopickup=true`, `pickupRadius=4`, `speed=2` |
| `magnet` | `magnet=true`, `speed=3`, `effects=true` |

## **How It Works**

Rail Boost runs on `VehicleMoveEvent`, which fires continuously as a minecart moves. On every move event, the plugin applies the cart's stored preset settings:

- **Speed:** The cart's velocity is compared against the target speed level. If the track ahead is considered straight and safe, the velocity factor is applied. Speed levels map to multipliers: 0.4, 0.8, 1.2, 2.0, 3.0, 4.0. Enhanced curve navigation and uphill momentum logic run simultaneously to prevent carts from slowing down or getting stuck.
- **Auto-Pickup:** Dropped items within the configured radius are collected and transferred to the cart's storage inventory, respecting the per-preset blacklist.
- **Speedometer:** A BossBar updates with the current velocity expressed in km/h, color-coded by speed range.
- **Chunk Loading:** Chunks ahead of the cart are temporarily force-loaded and released on a timer after the cart passes.
- **Magnetism:** Nearby minecarts within range receive a velocity nudge toward the cart, forming a convoy with collision prevention logic.
- **Effects:** Particles spawn behind the cart at an intensity proportional to current speed.

Minecart settings are stored in entity persistent data under the plugin key `settings`. Preset sticks carry the preset name in item persistent data - right-clicking a cart reads the stick's preset, looks it up in `presets.yml`, and writes the settings into the cart's persistent data.

Storage and hopper minecarts can be opened while riding using the F key (swap-hand event) for direct inventory access while in motion.

## **Commands**

### **Command Reference**

| Command | Description |
|---------|-------------|
| `/railboost help` | Show command help |
| `/railboost preset <name>` | Give yourself a preset stick for an existing preset |
| `/railboost give <player> <preset>` | Give another player a preset stick |
| `/railboost create <name>` | Create a new preset with default settings |
| `/railboost edit <preset> <setting> <value>` | Edit one setting on a preset |
| `/railboost edit <preset> storage` | Open shared storage inventory for a preset |
| `/railboost list` | List all available presets with summary settings |
| `/railboost delete <preset>` | Delete a preset |

**Aliases:** `/rb`, `/boost`

## **Permissions**

| Permission | Description | Default |
|------------|-------------|---------|
| `railboost.use` | Allows use of RailBoost features | `true` |
| `railboost.admin` | Administrative access to RailBoost | `op` |

## **Building from Source**

Rail Boost uses **Apache Maven** as its build system. The plugin is packaged as a standard JAR with no external runtime dependencies.

**Requirements:**
- Java 17 or newer
- Apache Maven 3.6 or newer

**Steps:**

```bash
# Clone the repository
git clone https://github.com/Cobbleworks/Rail-Boost-Plugin.git
cd Rail-Boost-Plugin

# Compile and package
mvn clean package
```

The output JAR is written to `target/RailBoost-x.x.x.jar`. Copy it into your server's `plugins/` folder as described in the [Installation Steps](#installation-steps) section.

**Project Structure:**

```
src/main/
├── java/de/railboost/
│   ├── RailBoostPlugin.java       - Plugin entry point (onEnable / onDisable)
│   ├── CommandManager.java        - All /railboost subcommands + tab completion
│   ├── MinecartController.java    - VehicleMoveEvent handling and speed/physics logic
│   ├── MinecartSettings.java      - Per-cart settings model and persistent data read/write
│   └── PresetManager.java         - Preset CRUD, YAML persistence, and shared storage
└── resources/
    ├── config.yml                 - Plugin configuration
    └── plugin.yml                 - Plugin metadata, commands, permissions
```

## **License**

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## **Screenshots**

The screenshots below demonstrate Rail Boost Plugin across several scenarios, including preset storage management, speed presets, particle effects, and the real-time speedometer.

<table>
  <tr>
    <th>Rail Boost - Preset Storage</th>
    <th>Rail Boost - Speed Preset</th>
  </tr>
  <tr>
    <td><a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-preset-storage.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-preset-storage.png" alt="Rail Boost preset storage" width="450"></a></td>
    <td><a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-speed-preset.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-speed-preset.png" alt="Speed preset on minecart" width="450"></a></td>
  </tr>
  <tr>
    <th>Rail Boost - Portal Particles</th>
    <th>Rail Boost - Collector Preset</th>
  </tr>
  <tr>
    <td><a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-portal-particles.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-portal-particles.png" alt="Portal particles on minecart" width="450"></a></td>
    <td><a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-collector-preset.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-collector-preset.png" alt="Collector preset on minecart" width="450"></a></td>
  </tr>
  <tr>
    <th>Rail Boost - Speedometer</th>
    <th>Rail Boost - Magnetic Carts</th>
  </tr>
  <tr>
    <td><a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-speedometer.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-speedometer.png" alt="Speedometer on rail path" width="450"></a></td>
    <td><a href="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-magnetic-carts.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/Cobbleworks/Rail-Boost-Plugin/raw/main/images/screenshot-magnetic-carts.png" alt="Magnetic minecart feature" width="450"></a></td>
  </tr>
</table>
