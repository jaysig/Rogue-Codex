# Git Security

Best practices for securing your Git workflow, protecting credentials, and maintaining safe collaboration practices.

## SSH Key Authentication

SSH keys provide secure, password-free authentication to Git repositories. This is the recommended method for accessing remote repositories.

### Generate SSH Keys

#### Modern Ed25519 Keys (Recommended)
```bash
# Generate Ed25519 key (faster, more secure)
ssh-keygen -t ed25519 -C "your-email@example.com"

# For older systems that don't support Ed25519
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"

# Save to default location: ~/.ssh/id_ed25519
# Set a strong passphrase when prompted
```

#### Multiple Keys for Different Services
```bash
# GitHub key
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519_github -C "github@example.com"

# GitLab key
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519_gitlab -C "gitlab@example.com"

# Work key
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519_work -C "work@example.com"
```

### Configure SSH Agent
```bash
# Start SSH agent
eval "$(ssh-agent -s)"

# Add key to agent
ssh-add ~/.ssh/id_ed25519

# Add key with passphrase to agent (macOS)
ssh-add --apple-use-keychain ~/.ssh/id_ed25519

# List keys in agent
ssh-add -l
```

### SSH Config for Multiple Keys
Create `~/.ssh/config`:
```bash
# GitHub
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_github
    AddKeysToAgent yes
    UseKeychain yes

# GitLab
Host gitlab.com
    HostName gitlab.com
    User git
    IdentityFile ~/.ssh/id_ed25519_gitlab
    AddKeysToAgent yes
    UseKeychain yes

# Work GitLab instance
Host work-gitlab
    HostName gitlab.company.com
    User git
    IdentityFile ~/.ssh/id_ed25519_work
    AddKeysToAgent yes
    UseKeychain yes
```

### Add Public Key to Services
```bash
# Copy public key to clipboard
# macOS:
pbcopy < ~/.ssh/id_ed25519.pub

# Linux:
xclip -sel clip < ~/.ssh/id_ed25519.pub

# Windows (Git Bash):
cat ~/.ssh/id_ed25519.pub | clip

# Or display key to copy manually
cat ~/.ssh/id_ed25519.pub
```

Then add to:
- **GitHub**: Settings → SSH and GPG keys → New SSH key
- **GitLab**: Preferences → SSH Keys → Add key
- **Bitbucket**: Account settings → SSH keys → Add key

### Test SSH Connection
```bash
# Test GitHub connection
ssh -T git@github.com

# Test GitLab connection
ssh -T git@gitlab.com

# Test with verbose output for debugging
ssh -vT git@github.com
```

## GPG Commit Signing

GPG signing verifies that commits actually came from you, providing authenticity and integrity.

### Generate GPG Key
```bash
# Generate GPG key
gpg --full-generate-key

# Choose options:
# 1. RSA and RSA (default)
# 2. 4096 bits
# 3. Key validity (0 = never expires, or set expiration)
# 4. Enter your name and email
# 5. Set secure passphrase
```

### Configure Git to Use GPG
```bash
# List GPG keys to find key ID
gpg --list-secret-keys --keyid-format LONG

# Configure Git with your key ID
git config --global user.signingkey YOUR_KEY_ID

# Enable automatic signing
git config --global commit.gpgsign true

# Enable signing for tags
git config --global tag.gpgsign true
```

### Add GPG Key to GitHub/GitLab
```bash
# Export public key
gpg --armor --export YOUR_KEY_ID

# Copy output and add to:
# GitHub: Settings → SSH and GPG keys → New GPG key
# GitLab: Preferences → GPG Keys → Add key
```

### Sign Commits and Tags
```bash
# Sign individual commit
git commit -S -m "feat: add secure authentication"

# Sign tag
git tag -s v1.0.0 -m "Release version 1.0.0"

# Verify signed commit
git log --show-signature

# Verify signed tag
git tag -v v1.0.0
```

## Credential Management

### Avoid Storing Passwords in Git
```bash
# ❌ Never do this:
git remote add origin https://username:password@github.com/user/repo.git

# ✅ Use SSH instead:
git remote add origin git@github.com:user/repo.git

# ✅ Or use credential manager:
git config --global credential.helper store
git config --global credential.helper cache
```

### Personal Access Tokens
For HTTPS authentication, use personal access tokens instead of passwords:

```bash
# Use token as password when prompted, or:
git remote set-url origin https://token@github.com/user/repo.git

# Better: use credential manager to store token securely
git config --global credential.helper manager-core  # Windows
git config --global credential.helper osxkeychain   # macOS
git config --global credential.helper libsecret     # Linux
```

### Environment Variables for Automation
```bash
# Set token in environment
export GITHUB_TOKEN="your_token_here"

# Use in automation scripts
git clone https://${GITHUB_TOKEN}@github.com/user/repo.git

# Or use GitHub CLI
gh auth login --with-token <<< "$GITHUB_TOKEN"
```

## Protecting Sensitive Information

### .gitignore Best Practices
```bash
# Always ignore sensitive files
.env
.env.local
.env.production
*.key
*.pem
config/secrets.yml
secrets/
credentials/

# Database files
*.db
*.sqlite
*.sqlite3

# IDE files that might contain paths
.vscode/settings.json
.idea/workspace.xml

# OS files
.DS_Store
Thumbs.db

# Logs that might contain sensitive data
*.log
logs/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
```

### Clean Sensitive Data from History
```bash
# Remove file from all history (use carefully)
git filter-branch --force --index-filter \
  'git rm --cached --ignore-unmatch path/to/sensitive/file' \
  --prune-empty --tag-name-filter cat -- --all

# Or use BFG Repo Cleaner (easier and faster)
java -jar bfg.jar --delete-files sensitive-file.txt
git reflog expire --expire=now --all
git gc --prune=now --aggressive

# Force push to update remote (⚠️ affects all collaborators)
git push --force --all origin
git push --force --tags origin
```

### Secrets Management
```bash
# Use environment variables
# .env file (ignored by git)
DATABASE_PASSWORD=secure_password_here
API_KEY=your_api_key_here

# Application code
const dbPassword = process.env.DATABASE_PASSWORD;
const apiKey = process.env.API_KEY;

# Docker secrets
docker secret create db_password password.txt
docker service create --secret db_password myapp

# Kubernetes secrets
kubectl create secret generic mysecret --from-literal=password=mypassword
```

## Repository Security

### Branch Protection
Configure branch protection on GitHub/GitLab:
```bash
# Typical protection rules:
# - Require pull request reviews
# - Require status checks to pass
# - Require branches to be up to date
# - Require signed commits
# - Restrict pushes to main branch
# - Require administrator review for changes
```

### Pre-commit Security Hooks
Install security scanning in pre-commit hooks:
```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/Yelp/detect-secrets
    rev: v1.4.0
    hooks:
      - id: detect-secrets
        args: ['--baseline', '.secrets.baseline']
  
  - repo: https://github.com/gitguardian/ggshield
    rev: v1.25.0
    hooks:
      - id: ggshield
        language: python
        stages: [commit]
```

### Dependency Security
```bash
# Check for vulnerable dependencies
npm audit
npm audit fix

# Python
pip-audit
safety check

# Ruby
bundle audit

# Use Dependabot or similar tools for automated updates
```

## Access Control

### Repository Permissions
```bash
# Principle of least privilege:
# - Read access: Can clone and pull
# - Write access: Can push to non-protected branches
# - Admin access: Can change settings, force push

# Use teams for organization-level access control
# Regularly audit who has access to repositories
```

### Token Scopes
When creating personal access tokens, use minimal scopes:
```bash
# GitHub token scopes:
# repo - Full repository access (use sparingly)
# public_repo - Public repository access only
# read:org - Read organization data
# workflow - GitHub Actions access

# Regularly rotate tokens
# Set expiration dates on tokens
# Use different tokens for different purposes
```

## Network Security

### HTTPS vs SSH
```bash
# SSH (recommended for regular use)
git clone git@github.com:user/repo.git

# HTTPS (good for automation with tokens)
git clone https://github.com/user/repo.git

# Always verify host keys on first connection
ssh -T git@github.com
```

### Corporate Networks
```bash
# Configure proxy if needed
git config --global http.proxy http://proxy.company.com:8080
git config --global https.proxy https://proxy.company.com:8080

# Or set environment variables
export HTTP_PROXY=http://proxy.company.com:8080
export HTTPS_PROXY=https://proxy.company.com:8080

# Bypass proxy for internal hosts
git config --global http.proxy.company.com ""
```

## Incident Response

### Compromised Credentials
If credentials are compromised:
```bash
# 1. Immediately revoke/rotate compromised credentials
# 2. Remove credentials from Git history
git filter-branch --force --index-filter \
  'git rm --cached --ignore-unmatch config/secrets.yml' \
  --prune-empty --tag-name-filter cat -- --all

# 3. Force push to all remotes
git push --force --all origin

# 4. Notify team members to re-clone repository
# 5. Review access logs for unauthorized activity
# 6. Update all systems using the compromised credentials
```

### Malicious Commits
```bash
# Verify commit signatures
git log --show-signature

# Check commit author vs committer
git log --pretty=fuller

# Revert malicious commits
git revert abc1234

# Or remove from history (if not yet shared)
git reset --hard HEAD~1
```

## Monitoring and Auditing

### Git Hooks for Security
Server-side hooks for additional security:
```bash
# pre-receive hook to reject large files
#!/bin/sh
max_size=10485760  # 10MB
while read oldrev newrev refname; do
    git diff --stat $oldrev..$newrev | while read line; do
        size=$(echo $line | awk '{print $3}' | sed 's/[^0-9]//g')
        if [ "$size" -gt "$max_size" ]; then
            echo "Error: File too large ($size bytes)"
            exit 1
        fi
    done
done
```

### Regular Security Audits
```bash
# Check for secrets in repository
git log -p | grep -i "password\|secret\|key\|token"

# Check recent commits from all contributors
git log --since="1 week ago" --pretty=fuller

# Verify all commits are signed
git log --show-signature | grep -c "gpg: Good signature"

# Check for suspicious file changes
git log --name-status | grep -E "\.(key|pem|p12|pfx)$"
```

## Best Practices Summary

### Do's
- ✅ Use SSH keys with strong passphrases
- ✅ Sign commits with GPG keys
- ✅ Use personal access tokens instead of passwords
- ✅ Regularly rotate credentials
- ✅ Enable branch protection rules
- ✅ Use pre-commit hooks for security scanning
- ✅ Keep dependencies updated
- ✅ Use .gitignore to prevent committing secrets
- ✅ Regular security audits

### Don'ts
- ❌ Never commit passwords or API keys
- ❌ Don't use shared accounts
- ❌ Don't disable SSL certificate verification
- ❌ Don't use weak SSH key passphrases
- ❌ Don't share private keys
- ❌ Don't force push to shared branches
- ❌ Don't ignore security warnings
- ❌ Don't use default credentials in code

## Emergency Contacts and Resources

- **GitHub Security**: https://github.com/security
- **GitLab Security**: https://about.gitlab.com/security/
- **Git Security Documentation**: https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work
- **OWASP Git Security**: https://owasp.org/www-project-code-review-guide/

---

*Last Updated: 2025-07-27*