# Zaum for Mac: releases

Zaum is a native terminal for macOS and iOS with persistent sessions, built for working with coding agents.
More at <https://jvcr.se/apps/zaum/>.

This repository has signed binaries only. It contains no source code.

## Download

- Latest DMG: see [Releases](https://github.com/jvcr/zaum-releases/releases/latest). Each release has the
  Developer ID signed, notarized and stapled `Zaum-<version>-<build>.dmg` and its SHA-256 in the notes.
- Stable link on the website: <https://jvcr.se/apps/zaum/Zaum-1.1.0.dmg>

## Updates

Installed copies update through Sparkle from
`https://github.com/jvcr/zaum-releases/releases/latest/download/appcast.xml`. Every update is
EdDSA-signed (`sparkle:edSignature`), and Sparkle refuses an update whose signature doesn't match the app's key.

## Checksums

Check a download with:

    shasum -a 256 Zaum-1.1.0-23.dmg

| Build | File | SHA-256 |
|---|---|---|
| 1.1.0 (23) | Zaum-1.1.0-23.dmg | `b011e154cc099040cd5d3d63bb607d6809a13a236b920a05254034c0eea79f5f` |
