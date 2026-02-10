# 🧭 Overview

The router was missing the IOS and there was no IOS on the SD Card in the router.


# ⚙️ Environment / Context
| Item                 | Details           |
| -------------------- | ----------------- |
| **System / Host**    | 2821 Cisco router |
| **OS / Version**     | Cisco IOS         |
| **Network Zone**     | Internal          |
| **Related Services** | OS                |
| **Impact Level**     | High              |


# 🚨 Problem Description

The router would not boot and would drop to ROMMON> 


# 🧰 Resolution Option 1


# TFTP


```
rommon > IP_ADDRESS=192.168.1.1
rommon > IP_SUBNET_MASK=255.255.255.0
rommon > DEFAULT_GATEWAY=192.168.1.2
rommon > TFTP_SERVER=192.168.1.2
rommon > TFTP_FILE=c2800nm-adventerprisek9-mz.124-13r.T11.bin
rommon > FE_PORT=0
rommon > FE_SPEED=100
rommon > FE_DUPLEX=full

```


## Synchnonization err:

- I set the PC to 100mb FULL duplex.


# 🧰 Resolution Option 2


- Format the SD Card on a working router.
- Then put that SD Card in a reader connected to Windows
- Copy the image to the SD Card
- Re-install the SD Card to the Router.

**NOTE:**
You cannot format the SD Card via Windows 10.
I think the file systems is FAT 16.


---

# 🧪 Verification / Testing

- Confirmed that the router booted and was functional.

---

# 📚 References

- Internal ticket: CABIT-2026-IOS

---

# 🏷️ Revision History
| Date       | Version | Author       | Changes         |
| ---------- | ------- | ------------ | --------------- |
| 2026-02-10 | 1.0     | C. Bumpstead | Initial article |


---





