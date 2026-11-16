# Day-1 setup on your Mac (C03) — do it yourself, step by step

> Doing it on the Windows PC too? Do this Mac setup first (or whichever device you use first), then follow SETUP-WINDOWS.md on the other device.

## 1. GitHub account
Sign up at github.com (if you don't have one). Pick a professional username — recruiters will see it.

## 2. Install the tools (Terminal)
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install git gh python
brew install --cask visual-studio-code
git --version && gh --version && python3 --version
```

## 3. Tell Git who you are
```bash
git config --global user.name "Shashwat Mishra"
git config --global user.email "<the email on your GitHub account>"
git config --global init.defaultBranch main
```

## 4. SSH key (lets your Mac talk to GitHub securely)
```bash
ssh-keygen -t ed25519 -C "<your GitHub email>"     # press Enter for defaults, set a passphrase
eval "$(ssh-agent -s)"
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
gh auth login     # GitHub.com → SSH → upload your key → login with browser
ssh -T git@github.com     # should greet you by username
```

## 5. Put this repo on GitHub
```bash
mkdir -p ~/code && cd ~/code
# unzip fde-bootcamp.zip here, then:
cd fde-bootcamp
git init
git add .
git commit -m "Day 1: bootcamp scaffold"
gh repo create fde-bootcamp --public --source=. --push
```

## 6. Private repo for CS50 problem sets
```bash
cd ~/code && mkdir cs50-private && cd cs50-private
git init && echo "# CS50 psets (private)" > README.md
git add . && git commit -m "init"
gh repo create cs50-private --private --source=. --push
```

## 7. The daily loop (end of every session)
```bash
cd ~/code/fde-bootcamp
cp logs/TEMPLATE.md logs/2026-11-17.md     # fill it in
git status                 # what changed?
git add .                  # stage the changes
git commit -m "Day 2: Missing Semester L2, shell scripting exercises"
git push                   # send to GitHub
```
Then paste the commit/folder link into the tracker's Daily Log and send your mentor check.
