# Hermes Mobile Client: releases

Signed Android builds of **Hermes Mobile Client**, an app that talks directly to your own
[Hermes](https://hermes-agent.nousresearch.com) gateway (`hermes serve`) from your phone.

This repository holds **release builds only**. The source lives in a private repository, and
releases are published here by CI so that the app can check for updates without a token.

> Latest: [v0.1.0](../../releases/tag/v0.1.0).

## What the app does

- Signs in to your gateway the same way Hermes Desktop does (RFC 8252 browser sign-in). Your
  password is typed on the gateway's own login page, never into the app.
- Live streaming chat with stop and steer, tool calls as compact rows.
- Session list: open, resume, search, rename, delete, start a new chat.
- Approvals and clarify questions answered from the phone.
- Model and reasoning-effort picker, and slash commands.
- Background notifications while a turn you started on the phone is running or waiting for you.
- Several gateways, one active at a time, tokens stored per gateway.
- In-app update from this repository.

## Install

1. Open **Releases** and download `HermesClient.apk` from the newest release.
2. Optional: compare its SHA-256 with the digest shown next to the asset.
3. Open the file on the phone and allow installing from that source when Android asks.
4. Open the app, add your gateway URL, and sign in.

Requires Android 8.0 (API 26) or newer.

## Updating

Settings has a **Check for updates** action, and the app checks once at startup. It reads the latest
release here, downloads the APK, checks its SHA-256 against the published digest, and refuses to
install on a mismatch. Android installs the update only if it is signed with the same key as the
installed app, so a build signed with any other key will not replace it.

## Security notes

- Tokens are kept in Keystore-backed encrypted storage and are excluded from backup. Signing out
  calls the gateway's logout and wipes that gateway's tokens.
- The app accepts any gateway URL, HTTP or HTTPS. On plain `http://` to a host that is not on your
  tailnet, the bearer token crosses the network unencrypted, and the app shows a warning. Prefer
  HTTPS or a private network such as Tailscale.
- The app contacts only the gateway you add and `api.github.com` / `github.com` for updates.

## Version history

See [CHANGELOG.md](CHANGELOG.md).

## Issues

The source repository is private. Report problems by opening an issue here.
