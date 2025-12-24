# Git LFS

- Overview
  - extension for Git to manage large binaries
  - stores pointers in repo, large files in LFS store

- Install
  - Debian/Ubuntu: `sudo apt install git-lfs`
  - macOS: `brew install git-lfs`
  - Init per repo: ```sh
    git lfs install
    ```

- Track files
  - add patterns to `.gitattributes`
  - examples:
    ```sh
    git lfs track "*.psd"
    git lfs track "*.zip"
    git add .gitattributes
    ```

- Add & commit
  - treat tracked files like normal files:
    ```sh
    git add bigfile.zip
    git commit -m "Add large asset"
    git push origin main
    ```

- Pulling & cloning
  - `git clone` downloads LFS pointers; run `git lfs pull` to fetch objects
  - or clone with LFS enabled: `GIT_LFS_SKIP_SMUDGE=0 git clone <repo>`

- Migrate existing history
  - rewrite history to move files into LFS (force-push required):
    ```sh
    git lfs migrate import --include="*.zip,*.mp4"
    git push --force origin main
    ```
  - WARNING: rewrites commits; coordinate with collaborators

- Hosting & quotas
  - GitHub/GitLab provide LFS storage and bandwidth quotas
  - monitor usage; consider external object storage if needed

- Best practices
  - track by pattern, not ad-hoc
  - avoid tracking small files (adds overhead)
  - commit `.gitattributes` first, then large files

- Troubleshooting
  - check env: `git lfs env`
  - auth errors: ensure tokens/SSH keys valid
  - smudge/clean filter errors: try `GIT_TRACE=1 git lfs pull`

- Useful commands
  - `git lfs install`
  - `git lfs track "pattern"`
  - `git lfs ls-files`  # list tracked files in history
  - `git lfs status`
  - `git lfs fetch --all`

- Resources
  - <https://git-lfs.github.com/>
  - <https://docs.github.com/en/repositories/working-with-files/managing-large-files>
