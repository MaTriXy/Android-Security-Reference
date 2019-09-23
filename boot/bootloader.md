## Unlocking

Unlock via `fastboot` for devices that allow it. See [Unlocking the bootloader](https://source.android.com/source/running.html#unlocking-the-bootloader).

> In	some	cases,	like	most	devices	built	for	use	on	the	Verizon	network,	the	ability	for	a	user	to	
unlock	the	bootloader	is	blocked	entirely.	(from [SamDunk][SamDunk])

## Security implications of unlocking

[Security risks of unlocking](http://android.stackexchange.com/questions/36830/whats-the-security-implication-of-having-an-unlocked-boot-loader).

Check out the `Verified Boot` section of this guide as it talks about unlocked bootloaders disabling verified boot in 7.0, which means its even more important in some cases that we know the state of it.

## Checking bootloader lock status

### SafetyNet

_EDIT: 20/10/16_ SafetyNet [now seems to check bootloader status](https://www.reddit.com/r/android/comments/587ss9/_/)! This has also been added to the [SafetyNet docs](https://developer.android.com/training/safetynet/attestation.html#compat-check-response)

### KeyAttestation

[Root of trust](https://developer.android.com/training/articles/security-key-attestation#certificate_schema_rootoftrust)

### Other

AFAIK there is no single and/or public apis/methods to check the bootloader lock status. OEMs have different private approaches for doing this. 

There is a system api [PersistentDataBlockManager](http://androidxref.com/7.0.0_r1/xref/frameworks/base/core/java/android/service/persistentdata/PersistentDataBlockManager.java#55) for this, which seems like it needs system permissions. Guessing exposed as a service and permissions controlled kernel level.

Some information about this appears in [Android 7.0 Compatibility Definition](http://source.android.com/compatibility/7.0/android-7.0-cdd.html#9_10_device_integrity) and is copied below

> Device implementations MUST correctly report through the System API method PersistentDataBlockManager.getFlashLockState() whether their bootloader state permits flashing of the system image. The FLASH_LOCK_UNKNOWN state is reserved for device implementations upgrading from an earlier version of Android where this new system API method did not exist.

See [SamDunk][SamDunk] for some mention of this and a related Samsung vuln.

> Manufacturers	employ	a	wide	variety	of	methods	and	mechanisms	to	determine	and	control	a
device’s	bootloader	lock	status.		Motorola	uses	TrustZone	protected	fuses,	HTC	uses	data	in	a	
write	protected region	of	eMMC,	and	some	LG	devices	use	a	signed	blob	in	the	boot	(kernel)	
partition.		There	are	likely	many	other	methods,	but	the	concept	is	the	same:	only	allow	the
unlock	status	to	be	changed	via	a	controlled	and	deliberate	method.	

  [SamDunk]: http://theroot.ninja/disclosures/SAMDUNK_1.0-03262016.pdf

## Updating

//TODO

