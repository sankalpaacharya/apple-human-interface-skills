# Privacy

> Being transparent about the data and device capabilities you need, and protecting whatever people let you access.

**Use it for:** Whenever you request a permission, collect personal data, or store sensitive information.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Permissions API + prompts (geolocation, `getUserMedia`, notifications), JIT consent, HTTPS, WebAuthn/passkeys |
| SwiftUI | Usage-description `Info.plist` keys, `CLLocationManager`/`AVCaptureDevice` requests, App Tracking Transparency, Keychain |
| Android (Compose) | Runtime permission requests (`rememberLauncherForActivityResult`), manifest declarations, EncryptedSharedPreferences/Keystore |
| React Native | `PermissionsAndroid` / `react-native-permissions`, `Keychain` secure storage, OS permission dialogs |
| Flutter | `permission_handler`, platform usage strings, `flutter_secure_storage`, local auth |

**Guidelines**
- Request only data/capabilities you actually need, and be specific.
- Ask in context — trigger the prompt when the user activates the feature, not at launch.
- Don't request on launch unless the feature is essential and the reason is obvious (e.g. maps needing location).
- Explain why before sensitive prompts with a clear single-purpose pre-prompt screen.
- Process data on-device where feasible to avoid risky round trips.
- Be transparent about collection and use; respect tracking limits.
- Don't deceptively prime consent prompts (no incentives, fake dialogs, or arrows at "Allow").

**Accessibility**
- Pre-permission explainer screens must be keyboard/screen-reader accessible with clear focus and one plainly-labeled action.
- Write rationale copy as a clear, active, sentence-case statement.

**Security (protecting data)**
- Use HTTPS everywhere; never send credentials over plain HTTP.
- Prefer passkeys/WebAuthn/biometrics or federated sign-in over passwords; add MFA if passwords remain.
- Store secrets in platform secure storage (Keychain, Keystore, secure storage), never plain text or `localStorage`.
- Use proven auth standards; don't invent custom schemes.

**Avoid**
- Up-front permission walls before the user shows intent.
- Manipulative or imitation consent prompts.
- Storing secrets in plain text or insecure client storage.

**Full reference:** [Apple HIG](../../references/foundations/privacy.md)
