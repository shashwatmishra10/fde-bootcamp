# Setup on your Windows PC

The Windows PC gets a Linux "room" (WSL / Ubuntu) so every command is identical to your Mac and to the courses (CS50, Missing Semester).

## 1. Install WSL (Linux inside Windows)
Open **PowerShell as Administrator** (Start → type PowerShell → right-click → Run as administrator):
```powershell
wsl --install
```
Restart the PC. An **Ubuntu** window opens → choose a Linux username + password (password won't show while typing — that's normal).
From now on, open the **Ubuntu** app whenever the Mac instructions say "Terminal".

## 2. Install the tools (inside Ubuntu)
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y git gh python3 python3-pip python3-venv
git --version && gh --version && python3 --version
```

## 3. Same Git identity as the Mac
```bash
git config --global user.name "Shashwat Mishra"
git config --global user.email "<the same email as on your Mac>"
git config --global init.defaultBranch main
```

## 4. A separate SSH key for this PC (each device gets its own ID card)
```bash
ssh-keygen -t ed25519 -C "<your GitHub email> (windows)"
gh auth login        # GitHub.com → SSH → upload this new key → login with browser
ssh -T git@github.com
```

## 5a. If the PC is your FIRST device (repo not on GitHub yet)
Your Windows Downloads folder is visible inside Ubuntu at `/mnt/c/Users/<your-windows-name>/Downloads`.
```bash
mkdir -p ~/code && cd ~/code
cp /mnt/c/Users/<your-windows-name>/Downloads/fde-bootcamp.zip . && sudo apt install -y unzip && unzip fde-bootcamp.zip
```
Then run steps 5 and 6 from SETUP.md (git init → commit → `gh repo create … --push`). Later, on the Mac, use step 5b instead.

## 5b. If the repo is ALREADY on GitHub — download (clone) it, don't create a new one
```bash
mkdir -p ~/code && cd ~/code
gh repo clone fde-bootcamp
gh repo clone cs50-private
```

## 6. VS Code
Install VS Code for Windows → install the **WSL** extension. Then from Ubuntu:
```bash
cd ~/code/fde-bootcamp && code .
```
Turn on **Settings Sync** (gear icon → Backup and Sync Settings → sign in with GitHub) on both devices so editor settings match.

## The two-device golden rule
| When | Command | Why |
|---|---|---|
| **Start** of every session (either device) | `git pull` | download what you pushed from the other device |
| **End** of every session | `git add .` → `git commit -m "..."` → `git push` | upload so the other device can get it |

Forget to push on one device → the other device won't have that work. If you ever see "merge conflict", stop and paste the message to your mentor.
