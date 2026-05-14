# Automatic Config Backup to GitHub — Klipper

> Automatically push your entire Klipper configuration to a private GitHub repository every time a file changes, on a schedule, or on reboot. If your SD card dies, your Pi fails, or you accidentally break your config, you can restore from GitHub in minutes.

---

## Why Back Up Your Config?

Your `printer.cfg`, macros, moonraker config, and slicer profiles represent hours of tuning work. None of it is backed up by default. A failed SD card, accidental file deletion, or a botched Klipper update can wipe everything instantly.

With automatic GitHub backup:
- Every config change is committed and timestamped automatically
- You have a full history — roll back to any previous working state
- Your config is accessible from anywhere
- Restoring to a new Pi takes minutes instead of hours

---

## The Tool — klipper-backup

**[→ GitHub: Staubgeborener/klipper-backup](https://github.com/Staubgeborener/klipper-backup)**
**[→ Full Documentation: klipperbackup.xyz](https://klipperbackup.xyz)**

klipper-backup is a lightweight script that connects your Klipper install to a GitHub repository and pushes your config files automatically. It supports:

- **File-change detection** — backs up the moment you save a config file
- **Scheduled backups** — runs on a cron schedule (e.g. every 4 hours)
- **Boot backup** — pushes a backup every time the Pi starts up
- **Manual backup** — run a single command any time you want a snapshot

It also integrates with KIAUH for easy installation.

---

## Before You Start

You will need:
- A **GitHub account** (free) — [github.com](https://github.com)
- A **Klipper printer** running on a Raspberry Pi or similar Linux host
- SSH access to your Pi (via PuTTY or terminal)
- Git installed on the Pi (installed in Step 1)

---

## Step 1 — Install Git on the Pi

Connect to your Pi via SSH and run:

```bash
sudo apt update && sudo apt install git -y
```

---

## Step 2 — Create a GitHub Repository

This will be the private repository your configs are pushed to.

1. Log in to [github.com](https://github.com)
2. Click the **+** icon (top right) → **New repository**
3. Give it a name — e.g. `klipper-backup` or `printer-config`
4. Set it to **Private** — your config may contain personal network details
5. **Do not** tick "Add a README file" — leave the repository empty
6. Click **Create repository**

---

## Step 3 — Generate a GitHub Personal Access Token

klipper-backup needs permission to push to your repository. You grant this via a Personal Access Token (PAT).

1. Go to **GitHub → Settings → Developer Settings → Personal access tokens → Fine-grained tokens**
2. Click **Generate new token**
3. Set a name (e.g. `klipper-backup-pi`)
4. Set an expiration — **No expiration** or 1 year
5. Under **Repository access**, select **Only select repositories** and choose your backup repo
6. Under **Permissions**, set:
   - **Contents** → Read and write
   - **Metadata** → Read-only
7. Click **Generate token**
8. **Copy the token immediately** — GitHub will not show it again

> ⚠️ Treat this token like a password. Store it somewhere safe (password manager). If you lose it, generate a new one.

---

## Step 4 — Install klipper-backup

### Option A — One-Line Install (Recommended)

From your Pi's SSH terminal:

```bash
curl -fsSL get.klipperbackup.xyz | bash
~/klipper-backup/install.sh
```

The install script will walk you through the initial setup interactively.

### Option B — Via KIAUH (version 6.0.0+)

If you use KIAUH to manage your Klipper install:

1. Run `~/kiauh/kiauh.sh`
2. Select **E — Extensions**
3. Select **4 — Klipper-Backup**
4. Follow the prompts

---

## Step 5 — Configure the .env File

After installation, open the configuration file:

```bash
nano ~/klipper-backup/.env
```

Fill in your details:

```ini
# === Required ===
github_token=ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx   # your Personal Access Token from Step 3
github_username=YourGitHubUsername              # your GitHub username
github_repository=klipper-backup               # the repository name you created in Step 2

# === Optional but recommended ===
commit_username=Klipper Backup                 # name shown in commit history
commit_email=your@email.com                    # email shown in commit history
use_filenames_as_commit_msg=true               # shows which files changed in each commit message
allow_empty_commits=false                      # don't push if nothing changed

# === Backup paths ===
# By default, backs up ~/printer_data/config/
# Add more paths as needed:
backupPaths=(
    "~/printer_data/config"
)

# === Exclude sensitive files ===
exclude=(
    "*.tmp"
    "*.bak"
)
```

Save with **Ctrl+O**, **Enter**, **Ctrl+X**.

---

## Step 6 — Choose Your Automation Method

Pick whichever method (or combination) suits your workflow:

---

### Option 1 — File-Change Detection (Recommended)

Backs up automatically the moment any config file is saved. This requires `inotify-tools`:

```bash
sudo apt install inotify-tools -y
```

Then enable the file-watch service:

```bash
sudo systemctl enable klipper-backup-filewatch.service
sudo systemctl start klipper-backup-filewatch.service
```

From now on, every time you save a file in your config folder, a backup is pushed to GitHub within seconds.

---

### Option 2 — Backup on Boot

Pushes a backup every time the Pi starts up — useful as a safety net even if you use another method as your primary:

```bash
sudo systemctl enable klipper-backup-on-boot.service
sudo systemctl start klipper-backup-on-boot.service
```

The service waits for a network connection before pushing, so it works reliably even if boot is fast.

---

### Option 3 — Scheduled Backup (Cron)

Backs up on a fixed schedule regardless of file changes. Open your crontab:

```bash
crontab -e
```

Add a line — this example backs up every 4 hours:

```
0 */4 * * * $HOME/klipper-backup/script.sh
```

Other useful schedules:

| Cron Expression | Schedule |
|---|---|
| `0 */4 * * *` | Every 4 hours |
| `0 2 * * *` | Once daily at 2am |
| `0 * * * *` | Every hour |
| `*/30 * * * *` | Every 30 minutes |

---

### Option 4 — Manual Backup

Run a backup any time with a single command:

```bash
~/klipper-backup/script.sh
```

You can also add this as a Klipper macro so you can trigger it from Mainsail or Fluidd:

```ini
[gcode_macro BACKUP_CONFIG]
gcode:
    RUN_SHELL_COMMAND CMD=backup_cfg

[gcode_shell_command backup_cfg]
command: ~/klipper-backup/script.sh
timeout: 30
verbose: True
```

> 💡 **Recommended setup:** Use **file-change detection** as your primary method and **backup on boot** as a safety net. That way you're covered whether configs change mid-session or after a reboot.

---

## Step 7 — Verify It's Working

Run a manual backup and check GitHub:

```bash
~/klipper-backup/script.sh
```

Then open your GitHub repository — you should see your config files committed with a timestamp. Your `printer.cfg`, `moonraker.conf`, macros, and any other files in your backup path should all be there.

---

## What Gets Backed Up

By default, everything inside `~/printer_data/config/` is backed up, which includes:

| File | What It Is |
|---|---|
| `printer.cfg` | Your main Klipper configuration |
| `moonraker.conf` | Moonraker API settings |
| `*.cfg` macro files | Custom macros and include files |
| `KlipperScreen.conf` | KlipperScreen settings (if installed) |
| Any other files you add to `backupPaths` | Fully configurable |

---

## Restoring From Backup

If you need to restore your config to a new or rebuilt Pi:

1. Set up Klipper fresh (via KIAUH)
2. Clone your backup repository to the Pi:

```bash
cd ~/printer_data/config
git clone https://github.com/YourUsername/klipper-backup .
```

3. Restart Klipper — your full config is restored

> 💡 Because every change is a separate commit, you can also restore to a specific point in time using `git checkout <commit-hash>` if you need to roll back a broken change.

---

## Common Problems

| Problem | Fix |
|---|---|
| `Permission denied` pushing to GitHub | Check your token has "Contents: Read and write" permission |
| Token expired | Generate a new token in GitHub settings and update `.env` |
| Files not being detected by file-watch | Check `inotify-tools` is installed; verify the path in `backupPaths` |
| Empty commits being pushed | Set `allow_empty_commits=false` in `.env` |
| Service not starting after reboot | Run `sudo systemctl status klipper-backup-on-boot.service` to check logs |

---

*Back to [Klipper Software Guides](../README.md#-klipper-software-guides--recommendations) | [README](../README.md)*
