# Managing Accounts

> Authentication and account flows that let people access their content without becoming a barrier to entry.

**Use it for:** Only when core functionality genuinely requires an account; otherwise let people use the app anonymously.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | OAuth/OIDC, Sign in with Apple/Google, passkeys via WebAuthn (`navigator.credentials`), `autocomplete="one-time-code"` autofill |
| SwiftUI | `SignInWithAppleButton` (`AuthenticationServices`), passkeys via `ASAuthorizationController`, Keychain autofill |
| Android (Compose) | Credential Manager API (passkeys + Sign in with Google), `Sign in with Google`, autofill framework |
| React Native | `@invertase/react-native-apple-authentication`, `@react-native-google-signin`, `react-native-passkey` |
| Flutter | `sign_in_with_apple`, `google_sign_in`, `firebase_auth`, passkey plugins |

**Guidelines**
- Require an account only if necessary; delay sign-in as long as possible (let users browse/try first).
- Explain the benefits of an account in the sign-in view — keep it brief and friendly.
- Prefer passkeys or federated sign-in (Apple/Google) over passwords; if using passwords, require 2FA.
- Name the auth method on the button ("Sign in with Passkey/Google"), not a generic "Sign In"; only show methods available on the device.
- Never prepopulate a password field; rely on the platform keychain/credential autofill.
- Provide a clear in-app path to delete the account (not just deactivate); don't bury it in Terms/Privacy.
- Tell people when deletion will complete and confirm when done; explain billing/cancellation relative to deletion.

**Accessibility**
- Make auth buttons real, descriptively labeled controls; announce error states via live region / VoiceOver / TalkBack.
- Support password managers and platform credential autofill with correct content-type tokens and labeled fields.

**Avoid**
- Forcing sign-in before any value is shown.
- Prefilling passwords, generic button labels, or hiding account deletion.

**Full reference:** [full reference](../../references/patterns/managing-accounts.md)
