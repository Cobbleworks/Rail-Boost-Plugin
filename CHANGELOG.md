# Changelog

All notable changes to Rail Boost will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased]

## [1.0.3] - 2026-04-28

Rail Boost v1.0.3 fixes the magnetic preset physics, replacing the old unbounded accumulation model with a proper spring-damper system that keeps carts stably anchored regardless of which cart the preset is applied to.

### Magnetic Physics Overhaul

- **Spring Model**: Force is now proportional to the displacement from a 1.5-block target spacing — carts attract when too far apart and gently resist when too close, preventing runaway overshooting
- **Damper Model**: Relative velocity along the cart axis is bled off each tick, eliminating the oscillation that caused carts to bounce and fly away after the first overshoot
- **Force Cap**: A hard MAX_FORCE limit (0.15) ensures speed-boost presets can never overpower the anchor force
- **Newton's Third Law**: The magnet cart now absorbs an equal counter-force, acting as a true anchor rather than a static reference point that other carts fly past

### Preset Adjustments

- **Magnet Preset Speed**: Removed the built-in `speed=3` from the default Magnet preset — speed boost and magnetic anchoring conflict fundamentally and caused the pulled cart to overshoot and oscillate

**Note:** If you encounter any bugs or issues, please don't hesitate to open an [issue](https://github.com/Cobbleworks/Rail-Boost-Plugin/issues). For any questions or to start a discussion, feel free to initiate a [discussion](https://github.com/Cobbleworks/Rail-Boost-Plugin/discussions) on the GitHub repository.

## [1.0.2] - 2026-04-01

Rail Boost v1.0.2 improves curve navigation reliability and anti-stuck handling for complex rail networks.

### Navigation Improvements

- **Curve Handling**: Improved direction-change detection for smoother transitions through curved track sections
- **Anti-Stuck Mechanisms**: Extended recovery logic for carts that stop unexpectedly on rails

**Note:** If you encounter any bugs or issues, please don't hesitate to open an [issue](https://github.com/Cobbleworks/Rail-Boost-Plugin/issues). For any questions or to start a discussion, feel free to initiate a [discussion](https://github.com/Cobbleworks/Rail-Boost-Plugin/discussions) on the GitHub repository.

## [1.0.1] - 2026-03-15

Rail Boost v1.0.1 delivers stability improvements and minor bug fixes following the initial release.

### Stability And Maintenance

- **General Refinements**: Applied maintenance updates for stability on long-running servers

**Note:** If you encounter any bugs or issues, please don't hesitate to open an [issue](https://github.com/Cobbleworks/Rail-Boost-Plugin/issues). For any questions or to start a discussion, feel free to initiate a [discussion](https://github.com/Cobbleworks/Rail-Boost-Plugin/discussions) on the GitHub repository.

## [1.0.0] - 2026-03-01

Rail Boost v1.0.0 is the initial release, delivering a full preset-driven minecart enhancement system with speed control, auto-pickup, shared storage, magnetism, and persistent configuration.

### Speed And Physics

- **Six Speed Levels**: Configurable speed levels from 0.4x to 4.0x with intelligent handling for curves, uphill sections, and speed transitions
- **Curve Navigation**: Enhanced curve detection with multi-block position checking for smooth travel through complex track networks
- **Chunk Loading**: Automatic chunk force-loading with timed unloading to ensure smooth travel across unloaded areas

### Preset And Storage System

- **Named Presets**: Create, save, and apply named minecart configurations using preset sticks via right-click
- **Three Built-In Presets**: Speed, Collector, and Magnet presets available immediately after installation
- **Preset-Linked Shared Storage**: Minecarts with presets share a 54-slot inventory accessible via commands and F-key while seated

### Automation And Effects

- **Auto-Pickup**: Automatic item collection within a configurable radius (1-5 blocks) with per-cart material blacklist
- **Magnetism System**: Minecart-to-minecart attraction for forming stable train convoys
- **Particle Trails**: Customizable particle effects with intensity scaling based on speed
- **Speedometer**: BossBar display showing real-time velocity in km/h with color-coded speed indicators

### Persistence

- **Per-Cart Settings**: All cart settings and preset data saved to YAML and restored across server restarts

**Note:** If you encounter any bugs or issues, please don't hesitate to open an [issue](https://github.com/Cobbleworks/Rail-Boost-Plugin/issues). For any questions or to start a discussion, feel free to initiate a [discussion](https://github.com/Cobbleworks/Rail-Boost-Plugin/discussions) on the GitHub repository.
