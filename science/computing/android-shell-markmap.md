# Android Shell

## Android vs Linux

### Similarities

- Linux kernel
  - Basic Unix/Linux commands work
- File management
  - `ls -l`
    - List files
  - `cd /data`
    - Change directory
  - `cp file1 file2`
    - Copy file
  - `mv file1 folder/`
    - Move file
  - `rm file.txt`
    - Delete file
  - `find <dir> -name "<name>"`
    - Exact match
  - `grep -r "term" /path/`
    - Full text search
- Process management
  - `ps -A`
    - Active processes
  - `top`
    - CPU usage
  - `kill 1234`
    - Kill process by PID
- Network
  - `ping 8.8.8.8`
    - Test connectivity
  - `ifconfig`
    - Network interfaces
  - `netstat -tulnp`
    - Active connections
- Storage
  - `df -h`
    - Disk space
  - `mount <partition>`
    - View mounts
  - `umount <partition>`
    - Unmount
- System info
  - `uname -a`
    - Kernel info
  - `cat /proc/cpuinfo`
    - CPU info
  - `logcat`
    - Android system logs

### Differences

- No GNU commands
  - Toybox or BusyBox instead
  - `sed`, `awk` may not work as expected
- No package manager
  - No `apt`, `dnf`, `yum`
  - Rooted device options
    - `pkg` (Termux)
    - `apk` (Alpine Linux via chroot/Proot)
- Different file structure
  - Android-specific hierarchy
  - Not standard Linux FHS

## File system structure

- `/system`
  - System files
  - Read-only
- `/data`
  - User data
  - App data
- `/sdcard`
  - External storage
  - Emulated storage
- `/vendor`
  - Vendor-specific files
- `/cache`
  - Temporary cache

## Shell environment

- Available shells
  - `/system/bin/sh`
    - Default shell
  - Busybox/Toybox
    - Limited commands
- Environment variables
  - `PATH`
  - `HOME`
  - `ANDROID_DATA`
- Permissions
  - User: shell (2000)
  - Limited access without root
- SELinux context
  - `getenforce`
    - Check mode
  - `setenforce`
    - Requires root

## Common tasks

- App management
  - `pm list packages`
    - List installed packages
  - `pm path <package>`
    - Get package path
  - `pm install <apk>`
    - Install package
  - `pm uninstall <package>`
    - Uninstall package
- Activity management
  - `am start <intent>`
    - Start activity
  - `am force-stop <package>`
    - Force stop app
- Service management
  - `service list`
    - List services
  - `service call <service>`
    - Call service
- Input simulation
  - `input text "hello"`
    - Input text
  - `input keyevent <code>`
    - Send key event
  - `input tap <x> <y>`
    - Tap screen
  - `input swipe <x1> <y1> <x2> <y2>`
    - Swipe gesture

## Termux

- Linux environment on Android
  - No root required
  - Package manager: `pkg`
- Install packages
  - `pkg install python`
  - `pkg install git`
  - `pkg install nodejs`
- Access shared storage
  - `termux-setup-storage`
  - `/data/data/com.termux/files/home/storage/`
- SSH server
  - `pkg install openssh`
  - `sshd`
