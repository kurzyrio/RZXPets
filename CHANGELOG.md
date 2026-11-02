# Changelog

All notable changes to the RZXPets project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.2] - 2026-11-03

### Security
- Fixed a block-break item duplication exploit by enforcing event cancellation checks and ignoreCancelled in block break listeners.
- Fixed an inventory deletion issue where non-GUI items on the player cursor were being wiped during shop and menu interactions.

### Added
- Integrated direct Vault economy support (`vault`, `money`, `economy`) as an alternative payment provider to zGems.
- Added database-level `extra_storage_limit` column and persistence in SQLite/MySQL for servers without LuckPerms.
- Added version-resilient particle resolution supporting both legacy and modern particle identifiers across Minecraft 1.20.4 through 1.21+.
- Added dynamic entity attribute lookup for maximum health across different Paper/Spigot versions.
- Added `rzxpets_entity` scoreboard tag and automated cleanup on startup to remove orphaned ghost pet entities.

### Changed
- Converted `RZXCore` dependency from a mandatory hard dependency to an optional soft dependency, allowing RZXPets to run standalone.
- Configured pet armor stand entities with `setPersistent(false)` to prevent them from persisting into chunk saves and leaking memory.
- Throttled WorldGuard region lookups to reduce CPU cycles during entity movement.
- Improved database reliability by wrapping queries in transactions with automatic rollback on SQL errors.
- Restored configurable premium edition handling in configuration files.

### Fixed
- Fixed memory leaks caused by lingering player entries in pet manager tracking maps upon pet despawn.
- Fixed redundant packet teleportation spam during pet following routines.

---

## [1.0.1] - 2026-11-02

### Added
- Implemented environment validation routines to detect server software capabilities and supported Paper/Spigot versions.
- Added lifecycle management for companion entities and event listeners.
- Added base companion registration system and initial pet configurations.

### Changed
- Standardized configuration loading procedures and default values in config.yml.
- Optimized pet entity tracking and update scheduling.

### Fixed
- Resolved entity despawn handling when players switch worlds or disconnect.
- Corrected item stack metadata serialization for custom pet items.

---

## [1.0.0] - 2026-11-02

### Added
- Initial release of RZXPets companion plugin for Minecraft Paper/Spigot servers.
- Core PetMechanic framework for companion traits, abilities, and particle effects.
- Interactive Shop and Pet Management graphical user interfaces.
- PlaceholderAPI hook integration for placeholders and statistics.
- Multi-database storage engine supporting SQLite and MySQL.
- Base permission structure, administrative commands, and reload support.
