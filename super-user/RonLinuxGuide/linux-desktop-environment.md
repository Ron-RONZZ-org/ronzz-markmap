  # Linux desktop environment

  - System checks
    - `echo $XDG_SESSION_TYPE` — check session type (x11/wayland)
    - `xprop -root | grep _NET_WM_CM_S0` — check compositor running

  - Shortcuts (GNOME examples)
    - `Alt+F10` — toggle maximize
    - `F11` — toggle fullscreen
    - `Ctrl+Alt+Up` — overview / workspace overview
    - `Ctrl+Alt+Left|Right` — switch workspaces

  - Default apps
    - set mime default: `xdg-mime default libreoffice-calc.desktop text/csv`
    - Desktop environments may override `xdg-mime`:
      - GNOME: Settings → Default Applications
      - KDE: System Settings → Applications → File Associations
      - XFCE: Settings → Preferred Applications

  - Input methods
    - IBus — default for many distributions
    - Fcitx5 — recommended for CJK/Asian input
    - Configure in GNOME: Settings → Region & Language → Input Sources
    - Tips
      - Use DE settings UI for associations when available (GNOME/KDE/XFCE).
      - For keyboard layouts and input-method issues, restart input daemon (`ibus-daemon --restart` or `fcitx5` service).


  - Managing app shortcuts in menu
    - Refresh desktop database:
      ```bash
      sudo update-desktop-database /usr/share/applications
      update-desktop-database ~/.local/share/applications
      ```

    - If still missing, create start menu shortcut manually:
      - Create `.desktop` in `~/.local/share/applications` (per-user) or `/usr/share/applications` (system-wide).
      - Minimal example (`myapp.desktop`):
        ```ini
        [Desktop Entry]
        Name=MyApp
        Comment=My application description
        Exec=/full/path/to/myapp %U
        Icon=/full/path/to/icon.png
        Terminal=false
        Type=Application
        Categories=Utility;Application;
        ```
      - Commands:
        ```bash
        mkdir -p ~/.local/share/applications
        cat > ~/.local/share/applications/{myapp}.desktop <<'EOF'
        [Desktop Entry]
        Name=MyApp
        Comment=My application
        Exec=/full/path/to/myapp %U
        Icon=/full/path/to/icon.png
        Terminal=false
        Type=Application
        Categories=Utility;
        EOF

        chmod +x ~/.local/share/applications/{myapp}.desktop
        update-desktop-database ~/.local/share/applications
        ```
      - Notes:
        - Use full paths for `Exec` and `Icon` or rely on commands in `PATH`.
        - For system-wide install put the file in `/usr/share/applications` (requires `sudo`).
        - If the app still doesn't appear, log out/in or run `gtk-launch myapp` to test.

