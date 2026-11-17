# Privacy Policy

Last updated 2026-11-17. Skalet was called Zaum, and Hjorden was called Ebenda (and briefly Semaro). Only the names changed.

- [Skalet](#skalet)
- [Hjorden](#hjorden)

## Skalet

Skalet collects nothing. There is no account, no analytics, no crash reporting SDK, no ads and no tracking. Apart from encrypted alerts passing through the push relay (see Alerts), the app sends nothing to the developer.

### Your terminal

What you type and what your shells print is encrypted end to end between your Mac and the iPhone or iPad you paired with it. When the two can reach each other, it goes directly from one to the other. When they can't, it passes through a relay that forwards it without being able to read it. The connection is QUIC with TLS 1.3, and each device holds its own private key. On the Mac that key is kept in the Keychain.

The developer of Skalet runs no server that receives or stores your sessions. Two services run by n0, the company behind iroh, help your devices find and reach each other. Here is what each of them can see.

### Who sees what

**n0's address service (dns.iroh.link).** While Sharing is on, the Skalet sessions helper on your Mac publishes a small signed record there. That's how your phone still finds the Mac after the Mac's IP address changes. The record holds the Mac's public key, which doubles as its connection id, and the address of its home relay: n0's relay, or yours if you set one. It holds no IP address, no name and nothing from your sessions. The Mac signs the record with its own key and refreshes it every few minutes while Sharing stays on. Like any server, the service sees the IP address the Mac publishes from.

The iPhone and iPad app publishes nothing there. To find your Mac it sends a plain lookup for the Mac's id, over HTTPS and DNS, the way a browser looks up a domain name. The lookup carries no key, token or signature from the phone, and nothing is registered for the phone. For that one request, the service sees the Mac's id and the phone's IP address.

**Relays.** An iroh relay forwards packets when your devices can't reach each other directly, and keeps a path open so the connection survives network changes. While the app is connected to your Mac, the phone keeps a connection to a relay. It proves to the relay that it holds its device key, and the relay knows it by its device id until it disconnects. A relay sees the device ids and IP addresses at both ends and how much traffic passes. It never sees content: everything that goes through it is end-to-end encrypted, and it has no key to open it. The phone uses n0's public relays. You can point the Mac at a relay you run yourself, and the phone then reaches the Mac through that relay.

So the outside services get ids and addresses, which they need to route the connection. Your session content only exists unencrypted on your Mac and on your phone.

### Alerts

With version 1.1.0 (38) or later on your Mac, alerts don't go through iCloud. When you allow notifications, the phone gives each paired Mac its push token and a key. The Mac encrypts each alert with that key, so only your phone can read it, and sends it to the developer's push relay, which runs on Cloudflare. The relay passes the push token and the encrypted alert to Apple's push service, which delivers it to your phone. The relay can't read the alert and keeps nothing. No terminal text, no account and nothing else goes there.

Macs with an older version still send alerts through iCloud, as described below.

### iCloud

If you're signed in to iCloud, Skalet uses your own private iCloud database (Apple's CloudKit). The developer can't read it. It holds:

- The list of your Macs and paired phones, so they can find each other.
- Pairing invites the Mac sends to your phone. The secret part sits in iCloud's encrypted fields.
- Alerts from Macs with an older version, such as "A command finished on Studio", deleted after a while. They never contain commands or output.

### Files and photos

When you open a file from the Mac, the phone downloads a copy to its cache. Forgetting a Mac deletes its downloads. If you save a downloaded image, it goes to your photo library. A photo you pick to send goes to the Mac over the same end-to-end encrypted connection, directly or through a relay that can't read it.

### Permissions

- Camera: only to scan the pairing QR code.
- Face ID: to unlock the app if you turn on the lock, and to confirm before Hjorden may reach your Macs.
- Microphone and Speech Recognition: only while you dictate. Speech is recognised on the device when your iPhone supports it; otherwise Apple's speech recognition service processes the audio. The developer never receives it.
- Photos: to pick a photo to send to the Mac, and to save a downloaded image to your library when you ask.
- Local network: to find your paired Mac on the same Wi-Fi.
- Notifications: for alerts, if you allow them.

### Contact

Questions? Email support@jvcr.se.

## Hjorden

Hjorden collects nothing. There is no account, no analytics, no crash reporting SDK, no ads and no tracking. Apart from encrypted alerts passing through the push relay (see Alerts), the app sends nothing to the developer.

### Your agents

What your agents write, the commands they ask to run and the answers you send back travel between your iPhone or iPad and your Mac over an end-to-end encrypted connection. When the two can reach each other, it goes directly from one to the other. When they can't, it passes through a relay that forwards it without being able to read it. The connection is QUIC with TLS 1.3, and each device holds its own private key.

The developer of Hjorden runs no server that receives or stores your sessions, transcripts or prompts. Two services run by n0, the company behind iroh, help your devices find and reach each other. They work the same way as for Skalet, and the [Skalet section](#skalet) explains what each of them can see. In short: they get device ids and IP addresses, which they need to route the connection, and never any content.

Messages, answers and photos you send to an agent go to that agent on your Mac, which may send them to its own AI provider under that provider's terms. Hjorden and Skalet send nothing to any AI provider themselves.

### Alerts

With Skalet 1.1.0 (38) or later on your Mac, alerts don't go through iCloud. When you allow notifications, the phone gives each paired Mac its push token and a key. When an agent needs you or finishes, the Mac encrypts the alert with that key, so only your phone can read it, and sends it to the developer's push relay, which runs on Cloudflare. The relay passes the push token and the encrypted alert to Apple's push service, which delivers it to your phone. The relay can't read the alert and keeps nothing. No terminal text, no account and nothing else goes there.

Macs with an older version still send alerts through iCloud, as described below.

### iCloud

If you're signed in to iCloud, Hjorden uses your own private iCloud database (Apple's CloudKit), which the developer can't read. It holds:

- The list of your Macs and paired phones, so they can find each other: each Mac's name and relay address, and for the phone its name and model (in iCloud's encrypted fields), the app version and whether alerts are on.
- Pairing offers your Mac sends to your phone. The secret part sits in iCloud's encrypted fields.
- Alerts from Macs with an older version, such as "An agent is waiting for you on Studio". When an agent asks something, the request text, the command and the choices are kept only in iCloud's end-to-end encrypted fields, and the alert is deleted after 7 days.

Hjorden also keeps the list of Macs it may connect to in your iCloud Keychain, so your other devices signed in to the same Apple ID know them too.

### On the phone

Hjorden keeps the list of your paired Macs and its device key on the phone. The home screen widgets and the Live Activity read a small summary that the app saves in its own storage on the phone: agent titles and states, the question an agent is waiting on, its current step and your usage limits. It doesn't leave the device.

A photo you attach goes to the Mac over the same end-to-end encrypted connection and is saved there as a file.

### Face ID

Face ID runs on the device through Apple's LocalAuthentication. Hjorden only learns whether the check passed. It never sees or stores your face data.

### Permissions

- Camera: only to scan the pairing QR code.
- Face ID: to unlock the app if you turn on the lock, and to confirm before you approve a command or send a reply to an agent.
- Local network: to find your paired Mac on the same Wi-Fi.
- Notifications: for alerts, if you allow them.
- Microphone and Speech Recognition: only while you dictate a message. Speech is recognised on the device when your iPhone supports it; otherwise Apple's speech recognition service processes the audio. The developer never receives it.
- Photos: only to pick a photo to send to your Mac.

### Contact

Questions? Email support@jvcr.se.
