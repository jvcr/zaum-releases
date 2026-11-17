# Skalet for Mac: releases

Skalet (formerly Zaum) is a native terminal for macOS and iOS with persistent sessions, built for working with coding agents.
Its iPhone and iPad companion for coding agents is Hjorden (formerly Ebenda).

- [Privacy](PRIVACY.md): [Skalet](PRIVACY.md#skalet), [Hjorden](PRIVACY.md#hjorden)
- [Support](SUPPORT.md): [Skalet](SUPPORT.md#skalet), [Hjorden](SUPPORT.md#hjorden)
- [Terms](TERMS.md)

This repository has signed binaries only. It contains no source code.

## Skalet for Mac

[Download the latest release](https://github.com/jvcr/zaum-releases/releases/latest) (DMG, macOS 15 or later).

- Latest DMG: see [Releases](https://github.com/jvcr/zaum-releases/releases/latest). Each release has the
  Developer ID signed, notarized and stapled `Zaum-<version>-<build>.dmg` and its SHA-256 in the notes.

## Hjorden

Hjorden is an iPhone and iPad app to watch and answer the coding agents running in Skalet on your Mac. It isn't on the App Store yet.
See its [privacy](PRIVACY.md#hjorden) and [support](SUPPORT.md#hjorden) sections.

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
