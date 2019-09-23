# SecureRandom

- [CDD](https://source.android.com/compatibility/7.0/android-7.0-cdd.html) doc contains no info on `SecureRandom`
- Src can be found at `libcore/luni/src/main/java/java/security/SecureRandom.java`

## Implmentations / Changes 

### Android 6

- new SecureRandom()  
  - If no `Services.getSecureRandomService()` then uses SHA1PRNG (provided by [`AndroidOpenSSL` and `Crypto`](http://stackoverflow.com/a/40913256/236743))
  - otherwise returns first `Engine.door.getService` service/provider that supports `SecureRandom`
  
### Android 7

- The `Crypto` provider was removed, which removed one of two SHA1PRNG implementations from stock android
- The javadoc has been [updated](https://developer.android.com/reference/java/security/SecureRandom.html) with test info (copied below)

> A cryptographically strong random number minimally complies with the statistical random number generator tests specified in FIPS 140-2, Security Requirements for Cryptographic Modules, section 4.9.1. Additionally, SecureRandom must produce non-deterministic output. Therefore any seed material passed to a SecureRandom object must be unpredictable, and all SecureRandom output sequences must be cryptographically strong, as described in RFC 1750: Randomness Recommendations for Security.

### Android 8

- [SecureRandom.getInstanceStrong](https://developer.android.com/reference/java/security/SecureRandom.html#getInstanceStrong())
  - Blog post about [differences](https://tersesystems.com/blog/2015/12/17/the-right-way-to-use-securerandom/)

## /urandom

- [Android empties the entropy pool, resulting in blocking, user perceived lag/poor performance](https://code.google.com/p/android/issues/detail?id=42265)
  - States since 2.3 Android has used `dev/urandom`
- [Myths about /dev/urandom](http://www.2uo.de/myths-about-urandom/)

## Links

- [android-developers.blogspot.co.uk] [Using Cryptography to Store Credentials Safely](http://android-developers.blogspot.co.uk/2013/02/using-cryptography-to-store-credentials.html)
- [android-developers.blogspot.co.uk] [Security "Crypto" provider deprecated in Android N](http://android-developers.blogspot.co.uk/2016/06/security-crypto-provider-deprecated-in.html)
- [android-developers.blogspot.co.uk] [Some SecureRandom Thoughts](http://android-developers.blogspot.co.uk/2013/08/some-securerandom-thoughts.html)
- [Ensure that SecureRandom is properly seeded](https://wiki.sei.cmu.edu/confluence/display/java/MSC63-J.+Ensure+that+SecureRandom+is+properly+seeded)
- [The Right Way to Use SecureRandom](https://tersesystems.com/blog/2015/12/17/the-right-way-to-use-securerandom/)
- [Difference between Random and SecureRandom](https://www.tutorialspoint.com/random-vs-secure-random-numbers-in-java)
