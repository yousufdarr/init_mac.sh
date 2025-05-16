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

### Direct Method (⚠️ Not Recommended)

```bash
curl -fsSL https://your-domain.com/initialise_mac.sh | bash
```

**Warning:** The direct method bypasses script review and can be dangerous. Always prefer the safe method above.

## ✨ Features

### Package Management
- Installs and configures Homebrew
- Configures tap:
  - buo/cask-upgrade

### Development Tools
- Essential CLI tools:
  - git
  - node
  - zsh (with completions and syntax highlighting)
  - mas (Mac App Store CLI)
  - gh (GitHub CLI)
  - gnupg
  - pinentry-mac

### Applications
- Visual Studio Code
- Ghostty (terminal emulator)
- Readdle Spark (email client)
- Google Chrome

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

## 🔧 Post-Setup Tasks

After the script completes:

```bash
# Generate a new GPG key
gpg --full-generate-key

# List your GPG keys
gpg --list-secret-keys --keyid-format=long
```

## 💻 Compatibility

- Designed for macOS with Apple Silicon
- Compatible with Intel Macs (automatically detects architecture)

## ⚠️ Notes

- Some changes require a system restart to take effect
- The script is idempotent (safe to run multiple times)
- Requires admin privileges for some operations (will prompt for sudo password)

## 🤝 Contributing

Feel free to fork and modify this script for your needs. If you make improvements, please consider submitting a pull request. 