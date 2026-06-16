# DJConnect App Releases

Public release repository for the DJConnect iOS, iPadOS and macOS apps.

DJConnect is a physical-style voice remote for your music. The Apple app pairs with the DJConnect Home Assistant integration and sends playback, queue, playlist and voice requests through Home Assistant. Spotify credentials and Home Assistant long-lived tokens are not stored in the app.

## Downloads

Use the latest GitHub Release in this repository for public app binaries:

- macOS: signed and notarized app archive when available.
- iOS/iPadOS: unsigned diagnostic build archive when available. Normal user distribution still goes through TestFlight or the App Store.

Source code and development history live in the private app repository. Public Home Assistant integration and documentation live at:

- Website: https://djconnect.dev
- Home Assistant integration: https://github.com/pcvantol/djconnect

## Requirements

- Home Assistant with the DJConnect integration installed and configured.
- Spotify Premium for playback control through Spotify.
- iPhone, iPad or Mac on the same local network as Home Assistant for pairing and local Client API callbacks.
- Local Network permission for discovery and pairing.
- Microphone permission for push-to-talk music requests.
- Speech Recognition permission only when foreground wake word / stemactivatie is enabled.

## Pairing

1. Open DJConnect on iOS, iPadOS or macOS.
2. Copy the visible pairing details from the app:
   - Koppelcode / Pairing code
   - Client API url
3. Open the DJConnect integration setup in Home Assistant.
4. Choose the iOS app or macOS app client type and paste the pairing details.
5. Wait for the app to show that pairing completed.

The app advertises itself through Bonjour/mDNS as `_djconnect._tcp` while its local Client API is active. Home Assistant may use discovery to find the app, but the app still validates pairing through the visible koppelcode.

## macOS Install Notes

For a signed and notarized macOS release:

1. Download the latest `.zip` or `.dmg` asset from Releases.
2. Open it and move `DJConnect.app` to `Applications`.
3. Launch DJConnect.
4. If macOS asks for Keychain access, allow it. DJConnect stores only its local pairing token there.

If macOS blocks the app, make sure you downloaded the notarized release asset from this repository and not a local development build.

## iOS and iPadOS

Unsigned iOS/iPadOS build archives are published here for diagnostics and internal validation when available. They are not a replacement for TestFlight or App Store distribution, and regular users cannot install them without Apple distribution signing.

Developers can build from the private app repository with their own Apple Developer Program team and provisioning profiles.

## Privacy

DJConnect does not collect or process personal data outside the app. Device tokens are stored locally in the platform Keychain. Diagnostics and logs are shared only when you explicitly copy them or open a GitHub issue yourself.

The app does not store Spotify credentials and does not store Home Assistant long-lived access tokens.

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

This repository is intentionally small and contains public release metadata and distributable artifacts only. Old releases may be cleaned up so that only the latest supported public release remains available.
