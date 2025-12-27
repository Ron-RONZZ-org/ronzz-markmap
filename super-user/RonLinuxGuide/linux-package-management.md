# Linux package management

- Debian & derivatives — APT
    - Commands:
        - `apt search {package}`
        - `apt show {package}`
        - `sudo apt install {package}`
        - `sudo apt remove {package}` (use `sudo apt purge` to remove config)
        - `sudo apt autoremove`
    - Repositories:
        - files: `/etc/apt/sources.list`, `/etc/apt/sources.list.d/`
        - keys: `/etc/apt/trusted.gpg.d/`
    - Python tools:
        - `sudo apt update`
        - `sudo apt install pipx -y`
        - `pipx install {package}`
        - Note: `pipx` installs CLI Python tools in isolated environments.

- Flatpak
    - List apps: `flatpak list --app --columns=application`
    - Install: `flatpak install {remote-or-local}`
    - Prefer Flatpak for desktop apps where available.

- Snap
    - Use when needed; prefer Flatpak for it is <a href="https://ronzz.org/gestionnaire-des-paquets-sur-linux-mint/" target="_blank">lighter</a>

- Package management notes
    - apt common actions: `sudo apt install|remove|upgrade`
    - cleanup: `sudo apt --purge autoremove`
    - update indexes: `sudo apt update`
    - If package not in distro: use a compatible release (e.g., replace `$(lsb_release -cs)` with `jammy`).
    - Example: add Cloudflare repo and install
        ```bash
        curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg \
            | sudo gpg --yes --dearmor -o /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg

        echo "deb [signed-by=/usr/share/keyrings/cloudflare-warp-archive-keyring.gpg] \
            https://pkg.cloudflareclient.com/ $(lsb_release -cs) main" \
            | sudo tee /etc/apt/sources.list.d/cloudflare-client.list

        sudo apt-get update && sudo apt-get install cloudflare-warp
        ```

    - Paths: `/etc/apt/sources.list.d/`, `/etc/apt/trusted.gpg.d/`

    - Tip: prefer official repos or vendor-signed packages when possible.