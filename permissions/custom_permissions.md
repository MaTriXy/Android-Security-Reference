# Custom Permissions

## Declaring custom permissions

See [\<permission\>](https://developer.android.com/guide/topics/manifest/permission-element.html)

## Vulns

- [commonsguy/cwac-security] [The Custom Permission Problem](https://github.com/commonsguy/cwac-security/blob/master/PERMS.md)
  - Below `L-5-21` custom permissions were defined by the first installed app that declared them
  - See [checkCustomPermissions()](https://github.com/commonsguy/cwac-security#usage-checkcustompermissions) for a pre L check.
