# Https CAs

> To provide a more consistent and more secure experience across the Android ecosystem, beginning with Android Nougat, compatible devices trust only the standardized system CAs maintained in AOSP. 

From [android-developers.blogspot] [Changes to Trusted Certificate Authorities in Android Nougat](http://android-developers.blogspot.co.uk/2016/07/changes-to-trusted-certificate.html)

### Dev/DEBUG settings

Starting in N can add custom trust anchors via xml which are used only for debug builds. Removes the vuln of accidentially leaving debug code in production. 

- [IO link](https://youtu.be/XZzLjllizYs?t=1405)
- [developer.android.com] [Network Security Configuration] (http://developer.android.com/preview/features/security-config.html).

### Chain info tools

- https://langui.sh/2009/03/14/checking-a-remote-certificate-chain-with-openssl/

# Enforcing Https

From [Protecting against unintentional regressions to cleartext traffic in your Android apps](https://security.googleblog.com/2016/04/protecting-against-unintentional.html)

- M+ `android:usesCleartextTraffic=”false”` in manifest for M+ (6.0+). [Docs](https://developer.android.com/guide/topics/manifest/application-element.html#usesCleartextTraffic)
- `StrictMode.VmPolicy.Builder.detectCleartextNetwork()` in development
- N+ `<network-security-config>` [developer.android.com] [Network Security Configuration] (http://developer.android.com/preview/features/security-config.html).

# Supported CipherSuites

- [User Agent Capabilities: Android 6.0](https://www.ssllabs.com/ssltest/viewClient.html?name=Android&version=6.0&key=129)

