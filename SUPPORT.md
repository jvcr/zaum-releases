# Support

Last updated 2026-11-17. Skalet was called Zaum, and Hjorden was called Ebenda (and briefly Semaro). Only the names changed.

- [Skalet](#skalet)
- [Hjorden](#hjorden)

## Skalet

Skalet is a terminal for the Mac with an iPhone and iPad app that attaches to its sessions. The phone app runs no shell of its own, so you need Skalet on a Mac first.

### Download for Mac

[Download the latest Skalet for Mac](https://github.com/jvcr/zaum-releases/releases/latest) (DMG, macOS 15 or later).

The app is signed with my Developer ID and notarized by Apple, so the first time you open it macOS shows its usual "Apple checked it for malicious software" dialog. The Mac app isn't on the Mac App Store, because it runs your shells outside the App Sandbox. Checksums and older builds are on the [Releases](https://github.com/jvcr/zaum-releases/releases) page.

### Pairing a phone

1. On the Mac, click the iPhone button in the title bar and turn on Sharing.
2. Open Skalet on the phone, tap Add a Mac and scan the QR code. No camera? Tap Paste a Link and paste the link from the Mac.
3. Tap Request Access. Both screens show a small picture. If they match, click Approve on the Mac.

If the Mac and the phone use the same Apple ID, the Mac can send the invite through iCloud and you skip the camera.

### Common questions

**The phone says it can't reach the Mac.** Check that the Mac is awake, online and has Sharing on. Skalet reconnects by itself when the network comes back.

**The connection shows Relay.** The phone couldn't reach the Mac directly, often because of the macOS Firewall or a strict network. It still works and stays encrypted. Allow the Skalet sessions helper in the macOS Firewall to connect directly on your local network.

**Alerts don't arrive.** Update Skalet on the Mac to 1.1.0 (38) or later, allow notifications for Skalet in Settings > Notifications, and open Skalet on the phone once while the Mac is online. The Mac then sends alerts even when the app is closed, and the phone and the Mac don't need the same Apple ID.

**How do I remove a phone?** On the phone, choose Unpair Mac. If the Mac is online it revokes the phone too.

### Requirements

macOS 15 or later, iOS and iPadOS 18 or later.

### Contact

Email support@jvcr.se and I'll help. Mention your macOS and iOS versions and what the app showed.

## Hjorden

Hjorden is an iPhone and iPad app for the coding agents running on your Mac. The agents run in Skalet on the Mac, so you need Skalet there first. The phone runs no agent and no shell of its own.

### Set up the Mac

[Download Skalet](https://github.com/jvcr/zaum-releases/releases/latest) (macOS 15 or later) and open it. Start your agent in a Skalet session as you normally would. Its card appears in Hjorden once the phone is paired.

### Pairing a phone

If Skalet is already paired on the phone: open Hjorden and tap Connect via Skalet. Skalet asks for Face ID, then the Mac shows one confirmation. Approve it and you're done.

Otherwise, with a QR code:

1. On the Mac, click the iPhone button in Skalet's title bar and turn on Sharing.
2. In Hjorden, tap Pair a Mac and scan the QR code. No camera? Tap Paste a Link and paste the link from the Mac.
3. Both screens show a small picture. If they match, click Approve on the Mac.

To add a second Mac later, open the Mac menu at the top of the inbox and choose Pair a Mac.

### Common questions

**The inbox is empty.** Hjorden lists agents running in the Mac's sessions. Start one in Skalet, or tap + Agent to start one from the phone.

**The phone says it can't reach the Mac.** Check that the Mac is awake, online and has Sharing on. Hjorden reconnects by itself when the network comes back.

**Alerts don't arrive.** Update Skalet on the Mac to 1.1.0 (38) or later, allow notifications for Hjorden in Settings > Notifications (or tap Turn on alerts for agents that need you in the inbox), and open Hjorden once while the Mac is online. The Mac then sends alerts even when Hjorden and Skalet are closed, and the phone and the Mac don't need the same Apple ID.

**I get agent alerts twice.** Skalet on the Mac has a setting to also alert in Skalet. It's off by default. Turn it off if you only want Hjorden to notify you.

**How do I remove a phone?** On the Mac, open the iPhone menu in Skalet's title bar and remove the phone there. It loses access right away.

### Requirements

iOS and iPadOS 18 or later, Skalet on macOS 15 or later.

### Contact

Email support@jvcr.se and I'll help. Mention your macOS and iOS versions and what the app showed.
