# DJConnect App Releases

DJConnect. Muziekbediening met karakter.

DJConnect lets you ask for music and get it personally announced through Home
Assistant. This repository is an internal handoff surface for unsigned Apple
build artifacts and non-secret release metadata for the DJConnect iOS, iPadOS
and macOS apps.

The Apple app pairs with the DJConnect Home Assistant integration and sends
playback, queue, playlist and voice requests through Home Assistant. Spotify
credentials and Home Assistant long-lived tokens are not stored in the app.

## Repository Scope

This repository is intentionally small and contains only internal unsigned
artifact handoff metadata. Source code and development history live in the
private DJConnect app source repository.

## Internal artifact handoff

Unsigned artifacts are traceable to an exact app-source SHA and may be used
only by the Apple Secure Distribution Relay for the maintainer's private
MacBook, iPhone and iPad. They are not public install packages.

Signed public macOS, iOS and iPadOS distribution is performed directly through
the separately approved App Store Connect process (TestFlight, App Store and
Mac App Store). It is not published from this repository.

Source code and development history live in the private app repository. Public Home Assistant integration and documentation live at:

- Website: https://djconnect.dev
- Home Assistant integration: https://github.com/pcvantol/djconnect

## Requirements

- Home Assistant with the DJConnect integration installed and configured.
- Spotify Premium for playback control through Spotify.
- A configured Home Assistant Assist pipeline with working STT and TTS for
  voice/DJ announcements.
- iPhone, iPad or Mac on the same local network as Home Assistant for pairing and local Client API callbacks.
- Local Network permission for discovery and pairing.
- Microphone permission for push-to-talk music requests.
- Speech Recognition permission only when foreground wake word / stemactivatie is enabled.

## Pairing

1. Open DJConnect on iOS, iPadOS or macOS.
2. Let Home Assistant discover the app through Bonjour/mDNS, or copy the visible
   pairing details from the app:
   - Koppelcode / Pairing code
   - Client API url
3. Open the DJConnect integration setup in Home Assistant.
4. Choose the iOS app or macOS app client type and paste the pairing details.
5. Wait for the app to show that pairing completed.

The app advertises itself through Bonjour/mDNS as `_djconnect._tcp` while its local Client API is active. Home Assistant may use discovery to find the app, but the app still validates pairing through the visible koppelcode.

Pairing creates a DJConnect bearer token for this app installation. Discovery
alone never marks the app as paired.

## Internal installation

The qualified macOS relay signs an exact manifest-bound unsigned artifact with
Developer provisioning profiles stored locally on the maintainer's MacBook,
then installs it only on the allowlisted private Apple device. Certificates,
private keys and provisioning profiles never enter GitHub or this repository.

## Privacy

DJConnect does not collect or process personal data outside the app. Device tokens are stored locally in the platform Keychain. Diagnostics and logs are shared only when you explicitly copy them or open a GitHub issue yourself.

The app does not store Spotify credentials and does not store Home Assistant long-lived access tokens.

## Related Links

- Website: [https://djconnect.pages.dev](https://djconnect.pages.dev)
- Home Assistant integration: [pcvantol/djconnect](https://github.com/pcvantol/djconnect)
- ESP firmware releases: [pcvantol/djconnect-firmware](https://github.com/pcvantol/djconnect-firmware)
- Raspberry Pi client releases: [pcvantol/djconnect-pi-releases](https://github.com/pcvantol/djconnect-pi-releases)

## Support

For Home Assistant integration issues, pairing problems, feature requests or release feedback, open an issue in:

https://github.com/pcvantol/djconnect/issues

When reporting app problems, include:

- app version;
- platform: iOS, iPadOS or macOS;
- Home Assistant DJConnect integration version;
- whether you are paired or in demo mode;
- redacted diagnostics/logs from the app.

Never paste bearer tokens, Spotify tokens, Home Assistant tokens or passwords into issues.

## Release Policy

This repository is intentionally small and contains internal unsigned artifact
handoff metadata only. It never publishes signed, notarized, TestFlight, App
Store or Mac App Store artifacts.

## Legal

Copyright (c) 2026 Peter van Tol. All rights reserved.

Spotify is a trademark of Spotify AB. DJConnect is not affiliated with,
endorsed by, or sponsored by Spotify AB.
