# Changelog

All notable changes to Hermes Mobile Client. Versions follow `major.minor.patch`, and a release tag is
`v<version>`.

## [Unreleased] (planned first release: 0.1.0)

### Added
- Gateway registry: add, edit, remove and switch gateways; tokens stored per gateway.
- Native sign-in (RFC 8252) through a Chrome Custom Tab; token refresh and logout.
- Session list with search, rename, delete and pull-to-refresh.
- Streaming chat with stop, steer and expandable tool rows; history loads over REST.
- Live link to the gateway with automatic reconnect and a Connected / Connecting / Offline indicator.
- Network awareness: the link goes offline immediately with no connectivity (a VPN such as
  Tailscale does not count as connectivity) and reconnects at once when it returns.
- Catch-up after a reconnect: missed events are replayed without duplicates, or the chat reloads if
  the gateway restarted.
- Approval and clarify cards; password and secret prompts are declined with "Answer this on the PC".
- Model and reasoning-effort picker; slash command suggestions.
- Background watch: a foreground service and notifications while a phone-started turn runs or needs you.
- Self-update from this repository with SHA-256 verification.

### Known limitations
- Chat shows plain text with basic code blocks; full Markdown rendering is not done yet.
- A clarify request with several questions answers only the first.
- Slash suggestions run only when tapped; pressing Enter sends the text as a normal message.
- Some slash commands that resolve to a prompt or composer text (`send`, `skill`, `prefill`,
  `alias`) show no result.
