# Trusted IPC

## Using Intents

Intent IPC trust hangs off the public signing key and custom permissions.

### Caller

- Check package name and signing key Intent will be directed to (via `PackageManager`)
  - [TrustedIntents](https://github.com/guardianproject/TrustedIntents/blob/master/trustedintents/src/info/guardianproject/trustedintents/TrustedIntents.java) can help with this
  
### Callee

- Check package name (and signing key) via `Activity.getCallingPackage()`
  - [TrustedIntents](https://github.com/guardianproject/TrustedIntents/blob/master/trustedintents/src/info/guardianproject/trustedintents/TrustedIntents.java) can help with this
- Custom permissions
  - Check the system to see if anyone holds the custom permission which is applied to the intent-filter in question
