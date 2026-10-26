## 1.4.8 - Minecraft 26.3 / DiscordSRV 1.30.5 compatibility

- Compile against Paper 26.3 and DiscordSRV 1.30.5 using Java 25.
- Refresh Discord channel mappings after DiscordSRV connects or reloads, without requiring a Staff Chat reload.
- Use immutable channel snapshots to avoid concurrent modifications between JDA callbacks and Bukkit configuration reloads.
- Avoid subscribing to a DiscordSRV instance that is present but disabled.
- Add GitHub Actions Maven build with a downloadable JAR artifact.

# Changelog

## DiscordSRV-Staff-Chat 1.4.7

### Optimization

- Cached DiscordSRV staff/admin channel resolution instead of resolving channels during every relay path.
- Reduced Discord listener work by filtering bot/webhook messages before scheduling Bukkit-thread delivery.
- Moved debug file writes off hot server paths.

### Stability

- Added explicit Discord hook state for unavailable, initializing, ready, degraded, and failed integration states.
- Centralized DiscordSRV subscribe/unsubscribe handling.
- Added rate-limited warnings when a linked Discord channel cannot be resolved.
- Refreshed cached Discord channels during `/managestaffchat reload`.

### Configuration

- Preserved separate staff/admin message sections in `messages.config.yml`.
- Updated project metadata to 1.4.7.

### Diagnostics

- Improved README troubleshooting for missing channels, duplicate messages, permissions, reloads, and Discord relay issues.
- Debug logging now avoids synchronous file writes from join/chat paths.
