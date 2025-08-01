# Tech Setup Guide - Rogue Codex

**Getting started with the Rogue Codex knowledge base and AI fitness guide**

*This guide assumes you have no technical background and will walk you through everything step-by-step.*

---

## 📋 What You'll Need

- A computer (Windows, Mac, or Linux)
- Internet connection
- About 30 minutes for setup
- No coding experience required!

---

## 🎯 What We're Setting Up

1. **Obsidian** - The app that makes everything work beautifully
2. **Claude Code** - AI assistant for the fitness guide (optional but recommended)
3. **Rogue Codex files** - The knowledge base itself

---

## 📱 Step 1: Download Obsidian

Obsidian is a free note-taking app that makes the Rogue Codex work like magic.

### For Windows:
1. Go to [obsidian.md](https://obsidian.md)
2. Click **"Download for Windows"**
3. Once downloaded, double-click the installer file
4. Follow the installation prompts (click "Next" through everything)
5. Launch Obsidian when installation completes

### For Mac:
1. Go to [obsidian.md](https://obsidian.md)
2. Click **"Download for macOS"**
3. Once downloaded, open the .dmg file
4. Drag Obsidian to your Applications folder
5. Open Applications and launch Obsidian
6. If you get a security warning, right-click Obsidian and select "Open"

### For Linux:
1. Go to [obsidian.md](https://obsidian.md)
2. Click **"Download for Linux"**
3. Choose the format for your distribution:
   - **.deb** for Ubuntu/Debian: `sudo dpkg -i obsidian_*.deb`
   - **.rpm** for Fedora/RHEL: `sudo rpm -i obsidian-*.rpm`
   - **AppImage**: Make executable and run: `chmod +x Obsidian-*.AppImage && ./Obsidian-*.AppImage`

---

## 💻 Step 2: Install Developer Tools (Recommended)

While not strictly required, these tools will give you the best experience and are needed for the AI fitness features.

### For Mac Users:

#### Install Homebrew (Package Manager)
1. Open **Terminal** (press Cmd+Space, type "terminal")
2. Copy and paste this command:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
3. Follow the prompts (may ask for your password)

#### Install iTerm2 (Better Terminal)
```bash
brew install --cask iterm2
```

#### Install Git
```bash
brew install git
```

#### Install Oh My Zsh (Better Shell)
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### For Windows Users:

#### Install Chocolatey (Package Manager)
1. Open **PowerShell as Administrator** (Right-click Start → "Windows PowerShell (Admin)")
2. Copy and paste this command:
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

#### Install Windows Terminal (Better Command Line)
```powershell
choco install microsoft-windows-terminal
```

#### Install Git
```powershell
choco install git
```

#### Install PowerShell 7 (Optional but recommended)
```powershell
choco install powershell-core
```

### For Linux Users:

#### Ubuntu/Debian:
```bash
# Update package list
sudo apt update

# Install Git
sudo apt install git

# Install Zsh
sudo apt install zsh

# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install curl (if not already installed)
sudo apt install curl
```

#### Fedora/RHEL:
```bash
# Install Git
sudo dnf install git

# Install Zsh
sudo dnf install zsh

# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

#### Arch Linux:
```bash
# Install Git
sudo pacman -S git

# Install Zsh
sudo pacman -S zsh

# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

## 📁 Step 3: Get the Rogue Codex Files

You need to download the Rogue Codex files to your computer.

### Option A: Using Git (Recommended if you installed it above)
1. Open your terminal/command prompt
2. Navigate to where you want the files:
```bash
cd ~/Documents  # Mac/Linux
cd C:\Users\[YourName]\Documents  # Windows
```
3. Clone the repository:
```bash
git clone https://github.com/jaysig/Rogue-Codex.git
```

### Option B: Simple Download (If you skipped Git installation)
1. Go to the Rogue Codex repository page: [https://github.com/jaysig/Rogue-Codex](https://github.com/jaysig/Rogue-Codex)
2. Click the green **"Code"** button
3. Select **"Download ZIP"**
4. Once downloaded, **extract/unzip** the file:
   - **Windows**: Right-click the ZIP file → "Extract All"
   - **Mac**: Double-click the ZIP file
   - **Linux**: Right-click → "Extract Here" or use `unzip filename.zip`

### 📂 Where to Put the Files
Choose a location you'll remember:
- **Windows**: `C:\Users\[YourName]\Documents\Rogue Codex`
- **Mac**: `/Users/[YourName]/Documents/Rogue Codex`
- **Linux**: `/home/[YourName]/Documents/Rogue Codex`

---

## 🔗 Step 4: Connect Obsidian to Rogue Codex

Now we'll tell Obsidian where to find your Rogue Codex files.

1. **Open Obsidian**
2. When it first launches, you'll see a welcome screen
3. Click **"Open folder as vault"**
4. Navigate to where you put the Rogue Codex files
5. Select the **"Rogue Codex"** folder
6. Click **"Open"**

🎉 **You should now see the Rogue Codex in Obsidian!**

---

## ⚙️ Step 5: Configure Obsidian (Optional but Recommended)

These settings will make your experience much better:

### Enable Useful Features:
1. Click the **gear icon** (⚙️) in the bottom left
2. Go to **"Core plugins"**
3. Make sure these are enabled (toggle them on):
   - ✅ **File explorer**
   - ✅ **Search**
   - ✅ **Graph view**
   - ✅ **Backlinks**
   - ✅ **Tag pane**

### Appearance Settings:
1. In Settings, go to **"Appearance"**
2. Choose a **theme** you like (Dark mode is popular)
3. Adjust **font size** if needed

---

## 🤖 Step 6: Set Up AI Fitness Guide (Optional)

To use the AI-powered fitness features, you'll need Claude Code.

### Get Claude Code:
1. Go to [https://www.anthropic.com/claude-code](https://www.anthropic.com/claude-code)
2. Sign up for a Claude account (free tier available)
3. Follow their installation instructions for your operating system

### Why Claude Code?
- Powers the conversational fitness tracking
- Understands natural language ("Just did squats 225x5")
- Routes you to specialized fitness coaches
- Generates workout plans and nutrition advice

### Using Without Claude Code:
You can still use all the fitness templates and guides manually - they're just regular markdown files you can edit in Obsidian!

---

## 🚀 Step 7: Start Using Rogue Codex

### First Things to Try:

1. **Explore the Structure**:
   - Click on **README.md** files in each section
   - Use the **graph view** to see how everything connects

2. **For Fitness Users**:
   - Open `Fitness Guide/README.md`
   - Check out `Fitness Guide/User_Interaction_Guide.md`
   - Try the demo files in `Fitness Guide/References/Demo/`

3. **For General Knowledge Management**:
   - Explore `Lessons Learned/` for templates
   - Check out `Tools/` for software evaluations
   - Browse `Company Registry/` for business research

### Navigation Tips:
- **Ctrl+O** (Windows/Linux) or **Cmd+O** (Mac): Quick file search
- **Ctrl+Shift+F** or **Cmd+Shift+F**: Search all content
- **Ctrl+G** or **Cmd+G**: Open graph view
- Click **[[links]]** to jump between notes

---

## 🔧 Troubleshooting

### "Package manager installation failed"
- **Mac**: Make sure you have Xcode command line tools: `xcode-select --install`
- **Windows**: Make sure you ran PowerShell as Administrator
- **Linux**: Update your package lists first: `sudo apt update`

### "Git command not found"
- Restart your terminal after installing Git
- On Windows, you may need to restart your computer
- Verify installation: `git --version`

### "I can't see the files in Obsidian"
- Make sure you selected the correct folder when opening the vault
- The folder should contain README.md and other markdown files
- If you used Git clone, the files are in a subfolder

### "Links aren't working"
- This is normal if you moved files around
- Obsidian will show broken links - you can fix them or ignore them

### "The fitness guide isn't responding"
- The AI features require Claude Code to be set up
- You can still use all the templates manually

### "Obsidian won't open"
- Try running as administrator (Windows) or check security settings (Mac)
- Make sure you downloaded from the official obsidian.md website

### "Terminal/Command Prompt issues"
- **Mac**: Try iTerm2 if regular Terminal has issues
- **Windows**: Use Windows Terminal or PowerShell instead of Command Prompt
- **Linux**: Make sure you're using bash or zsh shell

---

## 📱 Mobile Access (Optional)

Want to access your Rogue Codex on your phone?

1. **Obsidian Mobile** is available for iOS and Android
2. You can sync using:
   - **Obsidian Sync** (paid service, easiest)
   - **iCloud** (Mac/iOS users)
   - **Google Drive, Dropbox**, etc. (with some setup)

---

## 🎓 Learning More

### Obsidian Resources:
- [Obsidian Help](https://help.obsidian.md) - Official documentation
- [Obsidian Forum](https://forum.obsidian.md) - Community support
- YouTube: Search "Obsidian beginner tutorial"

### Rogue Codex Specific:
- Start with the README.md in the main folder
- Each section has its own README with specific guidance
- The `Lessons Learned/` section has templates for everything

---

## 🆘 Getting Help

### If You're Stuck:
1. **Check the README files** - They contain most answers
2. **Search the Obsidian forum** - Very helpful community
3. **YouTube tutorials** - Visual learners especially benefit
4. **Ask a tech-savvy friend** - Sometimes a quick screen share helps

### Common Beginner Mistakes:
- Opening the wrong folder in Obsidian
- Not extracting the ZIP file completely
- Trying to use AI features without Claude Code setup

---

## ✅ Success Checklist

You're ready to go when you can:
- [ ] Open Obsidian and see the Rogue Codex files
- [ ] Click on links between notes and they work
- [ ] Find the Fitness Guide section
- [ ] See the graph view with connected notes
- [ ] Edit a file and see your changes
- [ ] Open terminal/command prompt (if you installed dev tools)
- [ ] Run `git --version` and see a version number (if you installed Git)

**Congratulations! You're now ready to use the Rogue Codex! 🎉**

---

*Need help? The beauty of this system is that it works entirely on your computer - nothing to break, no accounts to manage (except optional Claude Code). Take your time and explore!*

---

*Last Updated: 2025-08-01*