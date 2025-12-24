# Bootloader unlock on Huawei Kirin CPUs with PotatoNV

## PotatoNV v2.2.1

- [User manual](https://kutt.it/pnv-en)

## Process summary
  1. Verify images
  2. Upload hisi960 files
  3. Wait for device
  4. Connect and identify
  5. Write protection blocks
  6. Reboot
  7. Generate unlock code

## Multiple unlock attempts required

### Each generates new code
### Keys change with each run

### First attempt

- Verifying images
- Uploading hisi960
  - xloader
  - uce
  - fastboot
- Device info
  - Serial: CSX0218224000396
  - Board ID: 024NNK1798000905
  - Model: STF-AL10
  - Build: STF-AL10 9.1.0.201(C00E100R1P9)
- Status
  - FBLOCK state: unlocked
  - Saved key: UUUUUUUUUUUUUUUU
- Operations
  - Writing FBLOCK
  - Writing WVLOCK
  - Writing USRKEY
  - Rebooting
- Result
  - Unlock code: FMFZQBY64R6CZ0N7

### Second attempt

- Device info (same)
- Status
  - FBLOCK state: unlocked
  - Saved key: FMFZQBY64R6CZ0N7
- Operations (same)
- Result
  - Unlock code: TGJZVVGOJF63CCYP

### Third attempt

- Device info (same)
- Status
  - FBLOCK state: unlocked
  - Saved key: TGJZVVGOJF63CCYP
- Operations (same)
- Result
  - Unlock code: V0FIJR5FG6JVQH90
### Finally

- ```bash
  fastboot oem unlock {key}
  fastboot oem get-bootinfo
  ```


