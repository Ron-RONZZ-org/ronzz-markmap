# Android Basics

## Emulated Storage

- Concept
  - Folder within system disk
  - Own file table
  - Separate from partitions
- Purpose
  - System isolation
  - Apps isolation
  - Use all available disk space
- Location
  - `/storage/emulated/0/`
- Structure
  - DCIM
    - Camera photos
  - Downloads
    - Browser downloads
  - Documents
    - User documents
  - Music, Pictures, Videos
    - Media files

## File system

- Root directory
  - `/`
- System directories
  - `/system`
    - System apps
    - Libraries
  - `/data`
    - User apps
    - App data
  - `/vendor`
    - Hardware-specific files
  - `/sdcard`
    - Symlink to emulated storage

## Permissions

- Storage permissions
  - READ_EXTERNAL_STORAGE
  - WRITE_EXTERNAL_STORAGE
- Android 10+
  - Scoped storage
  - MediaStore API
- Android 11+
  - MANAGE_EXTERNAL_STORAGE
  - All files access

## Package management

- APK files
  - Android Package
  - Installation format
- Package manager
  - Install/uninstall apps
  - `pm` command
- System apps
  - Pre-installed
  - Require root to remove

## Android Debug Bridge

- ADB
  - Communication with device
  - Command-line tool
- Common commands
  - `adb devices`
  - `adb shell`
  - `adb install`
  - `adb pull/push`

## Security

- SELinux
  - Security-Enhanced Linux
  - Enforcing mode
- File-Based Encryption
  - FBE
  - Android 7.0+
  - Per-user encryption
- Verified Boot
  - Chain of trust
  - Boot integrity
