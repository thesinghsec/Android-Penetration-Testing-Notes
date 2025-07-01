# Example: Signing and Verifying an APK

---

##  Signing an APK

Use the **`apksigner`** tool to sign an unsigned APK:

```bash
apksigner sign --ks my-release-key.jks --out my-app-release.apk my-app-unsigned.apk
````

---

##  Verifying an APK

Use the **`apksigner`** tool to verify the APK’s signature:

```bash
apksigner verify --verbose my-app-release.apk
```

---

##  Why Is This Important for Pentesting?

* APK signing **ensures the integrity and authenticity** of apps.
* Example:

  * If an attacker tampers with an APK (e.g., injects malicious code), the signature becomes invalid.
  * Exploiting weaknesses in the signing process can enable the installation of malicious apps on user devices.

```
