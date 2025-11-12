---
title: <Concise Article Title>
category: <System | Process | Hardware | Software | Security | etc.>
tags:
  - KB
  - Fault
  - Resolution
created: 2025-11-12
updated: YYYY-MM-DD
author: Craig Bumpstead
status: Draft | Published | Archived
confidence: 🔹 (High / Medium / Low)
description: "*** I used AI to make this look more pleasing to the eye."
---

# 🧭 Overview

Installation of VICE on Arch Linux, did not create icons in the Whisker Menu of XFCE3.

---

# ⚙️ Environment / Context
| Item                 | Details                |
| -------------------- | ---------------------- |
| **System / Host**    | Linux Workstation      |
| **OS / Version**     | ARCH Linux             |
| **Network Zone**     | Internal (cabit.local) |
| **Related Services** | Whisker Menu / VICE    |
| **Impact Level**     | Low                    |

---

# 🚨 Problem Description


```
The installation of VICE worked as expected via yay, however there were no icons in the whisker menu.
```

---

# 🔍 Root Cause Analysis

Possible issue with AUR package

---

# 🧰 Resolution Steps
Step-by-step fix or workaround, with commands or configuration snippets.

1. Check that the icons exist:
   ``` bash
   pacman -Ql vice | grep -E '\.png|\.svg|\.xpm'

   ```
2. Create desktop file:
   ```
   vim ~/.local/share/applications/xvic.desktop
   ```
3. File contents:

		[Desktop Entry]
		Version=1.0
		Type=Application
		Name=VICE VIC-20 Emulator
		Comment=Run Commodore VIC-20 emulator (xvic)
		Exec=/usr/bin/xvic
		Icon=/usr/share/vice/common/VIC20_32.png
		Terminal=false
		Categories=Game;Emulator;


    
3. Set correct permissions on file:

```
chmod +x ~/.local/share/applications/xvic.desktop
```

4. Restart the Desktop:

```
xfdesktop --reload
```


---

# 🧪 Verification / Testing

- Confirmed that the icon was present and functional.

---

# 📚 References

- Internal ticket: CABIT-2025-VICE1

---

# 🏷️ Revision History
| Date       | Version | Author       | Changes                       |
| ---------- | ------- | ------------ | ----------------------------- |
| 2025-11-12 | 1.0     | C. Bumpstead | Initial article               |


---
