# macOS System Setup Script

This script automates the setup of a fresh macOS system with development tools, applications, and system configurations.

## 🚨 Security Warning

Before running this script, please:
1. **Download and review** the script instead of running directly from the internet
2. **Understand what it does** before executing
3. **Never** run as root/sudo

## 🚀 Usage

### Safe Method (Recommended)

```bash
# Download the script
curl -O https://your-domain.com/initialise_mac.sh

# Review the script content
less initialise_mac.sh

# Make it executable
chmod +x initialise_mac.sh

# Run the script
./initialise_mac.sh
```

### ⚠️ Direct Method (Not Recommended)

```bash
curl -fsSL https://your-domain.com/initialise_mac.sh | bash
```

**Warning:** The direct method bypasses script review and can be dangerous. Always prefer the safe method above.

## ✨ Features

### Package Management
- Installs and configures [Homebrew](https://brew.sh/)
- Configures tap:
  - [buo/cask-upgrade](https://github.com/buo/homebrew-cask-upgrade)

### Development Tools
- Essential CLI tools:
  - [git](https://git-scm.com/)
  - [node](https://nodejs.org/)
  - [zsh](https://www.zsh.org/) (with [completions](https://github.com/zsh-users/zsh-completions) and [syntax highlighting](https://github.com/zsh-users/zsh-syntax-highlighting))
  - [mas](https://github.com/mas-cli/mas) (Mac App Store CLI)
  - [gh](https://cli.github.com/) (GitHub CLI)
  - [gnupg](https://gnupg.org/)
  - [pinentry-mac](https://github.com/GPGTools/pinentry-mac)

### Applications
- [Visual Studio Code](https://code.visualstudio.com/)
- [Ghostty](https://ghostty.dev/) (terminal emulator)
- [Readdle Spark](https://sparkmailapp.com/) (email client)
- [Google Chrome](https://www.google.com/chrome/)

### Development Fonts
TBD

### System Configuration
- Shows hidden files in Finder
- Sets optimal key repeat rates
- Configures Finder preferences
- Disables boot sound
- Shows file extensions globally
- Enables Finder status and path bars

### GPG Setup
- Configures GPG for secure commit signing
- Sets up pinentry-mac for password prompts
- Configures GPG agent with sensible cache timeouts
- Adds necessary environment variables to shell

## �� Post-Setup Tasks

### 1. GPG Key Generation

After the script completes, you can set up your GPG key:

```bash
# Generate a new GPG key
gpg --full-generate-key
# Use RSA and RSA, 4096 bits, and your GitHub email

# List your key ID
gpg --list-secret-keys --keyid-format=long

# Configure Git
git config --global user.signingkey YOUR_KEY_ID
git config --global commit.gpgsign true

# Export your public key for GitHub
gpg --armor --export YOUR_KEY_ID
```

Add to GitHub:
1. Copy the exported GPG key
2. Go to GitHub Settings → SSH and GPG keys
3. Click "New GPG key"
4. Paste your public key

### 2. Shell Configuration

The script configures Zsh with syntax highlighting. You may want to:
- Choose a different theme
- Add additional plugins
- Customize your prompt

## 💻 Compatibility

- Designed for macOS with Apple Silicon
- Compatible with Intel Macs (automatically detects architecture)

## 📝 Notes

- Some changes require a system restart to take effect
- The script is idempotent (safe to run multiple times)
- Requires admin privileges for some operations (will prompt for sudo password)

## 🤝 Contributing

Feel free to fork and modify this script for your needs. If you make improvements, please consider submitting a pull request. 