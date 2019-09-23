# NDK Notes

> Users should have a consistent app experience across updates, and developers shouldn’t have to make emergency app updates to handle platform changes. For that reason, we recommend against using private C/C++ symbols. Private symbols aren’t tested as part of the Compatibility Test Suite (CTS) that all Android devices must pass. They may not exist, or they may behave differently. This makes apps that use them more likely to fail on specific devices, or on future releases --- as many developers found when Android 6.0 Marshmallow switched from OpenSSL to BoringSSL.

> Note: SSL/crypto is a special case, applications must NOT use platform libcrypto and libssl libraries directly, even on older platforms. All applications should use GMS Security Provider to ensure they are protected from known vulnerabilities.

From [Android changes for NDK developers
](https://android-developers.googleblog.com/2016/06/android-changes-for-ndk-developers.html)

# Standalone libs

See [/libs/crypto.md](/libs/crypto.md)
