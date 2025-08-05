# Git Installation

A guide to installing and initially configuring Git on your system.

## Prerequisites
- Windows 10+, macOS 10.15+, or Linux
- Internet connection for downloading

## Step 1: Install Git

### macOS
```bash
# Using Homebrew (recommended)
brew install git

# Or download from https://git-scm.com/download/mac
```

### Ubuntu/Debian Linux
```bash
sudo apt update
sudo apt install git
```

### Windows
Download the installer from [https://git-scm.com/download/win](https://git-scm.com/download/win) and run it.

During installation:
- Choose "Use Git from the Windows Command Prompt"
- Choose "Checkout Windows-style, commit Unix-style line endings"
- Choose "Use Windows' default console window"

## Step 2: Initial Configuration

After installation, configure Git with your identity:

```bash
# Set your name (used in commits)
git config --global user.name "Your Name"

# Set your email (used in commits)
git config --global user.email "your-email@domain.com"

# Set default branch name to 'main' (modern standard)
git config --global init.defaultBranch main
```

### Configure Default Editor
```bash
# VS Code (if installed)
git config --global core.editor "code --wait"

# Vim (pre-installed on most systems)
git config --global core.editor "vim"

# Nano (user-friendly for beginners)
git config --global core.editor "nano"
```

### Optional: Configure Line Endings
```bash
# Windows
git config --global core.autocrlf true

# macOS/Linux
git config --global core.autocrlf input
```

## Step 3: Verify Installation

Check that Git is installed and configured correctly:

```bash
# Check Git version
git --version

# View your configuration
git config --list

# View specific settings
git config user.name
git config user.email
```

You should see output similar to:
```
git version 2.39.0
user.name=Your Name
user.email=your-email@domain.com
init.defaultbranch=main
core.editor=code --wait
```

## Step 4: First Repository Test

Create a test repository to verify everything works:

```bash
# Create a test directory
mkdir git-test
cd git-test

# Initialize a Git repository
git init

# Create a test file
echo "Hello Git!" > test.txt

# Add and commit the file
git add test.txt
git commit -m "Initial commit"

# Check the log
git log --oneline
```

If you see your commit in the log, Git is working correctly!

## Next Steps

- **[Git Essential Commands](Git%20Essential%20Commands.md)** - Learn basic Git operations
- **[Git Security](Git%20Security.md)** - Set up SSH keys for secure access to remote repositories

---

*Last Updated: 2025-07-27*