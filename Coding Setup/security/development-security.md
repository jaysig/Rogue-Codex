# Development Security Guide

A comprehensive guide to implementing security best practices in development environments, focusing on API key management, environment variables, Git security, and package scanning.

## Overview

Development security is crucial for protecting your code, data, and infrastructure. This guide covers essential security practices for modern development workflows.

## API Key Management

### Secure Storage

#### Environment Variables
```bash
# Set environment variables
export API_KEY="your-secret-key"
export DATABASE_URL="your-database-url"
export JWT_SECRET="your-jwt-secret"

# Add to shell profile
echo 'export API_KEY="your-secret-key"' >> ~/.zshrc
echo 'export DATABASE_URL="your-database-url"' >> ~/.zshrc
source ~/.zshrc
```

#### .env Files
```bash
# Create .env file (never commit this)
cat > .env << EOF
API_KEY=your-secret-key
DATABASE_URL=your-database-url
JWT_SECRET=your-jwt-secret
STRIPE_SECRET_KEY=sk_test_your-stripe-key
AWS_ACCESS_KEY_ID=your-aws-key
AWS_SECRET_ACCESS_KEY=your-aws-secret
EOF

# Add to .gitignore
echo ".env" >> .gitignore
echo ".env.local" >> .gitignore
echo ".env.*.local" >> .gitignore
```

#### .env.example Template
```bash
# Create .env.example (safe to commit)
cat > .env.example << EOF
API_KEY=your-api-key-here
DATABASE_URL=your-database-url-here
JWT_SECRET=your-jwt-secret-here
STRIPE_SECRET_KEY=sk_test_your-stripe-key-here
AWS_ACCESS_KEY_ID=your-aws-key-here
AWS_SECRET_ACCESS_KEY=your-aws-secret-here
EOF
```

### Best Practices

#### Key Rotation
```bash
# Script to rotate API keys
#!/bin/bash
# rotate-keys.sh

echo "Rotating API keys..."

# Generate new keys
NEW_API_KEY=$(openssl rand -hex 32)
NEW_JWT_SECRET=$(openssl rand -hex 64)

# Update .env file
sed -i "s/API_KEY=.*/API_KEY=$NEW_API_KEY/" .env
sed -i "s/JWT_SECRET=.*/JWT_SECRET=$NEW_JWT_SECRET/" .env

echo "API keys rotated successfully"
```

#### Access Control
```bash
# Restrict file permissions
chmod 600 .env
chmod 600 ~/.ssh/id_rsa

# Set proper ownership
chown $USER:$USER .env
```

## Environment Variable Security

### Configuration Management

#### Development vs Production
```bash
# Development environment
export NODE_ENV=development
export DEBUG=true
export LOG_LEVEL=debug

# Production environment
export NODE_ENV=production
export DEBUG=false
export LOG_LEVEL=error
```

#### Environment-Specific Files
```bash
# .env.development
API_KEY=dev-api-key
DATABASE_URL=postgresql://localhost/dev_db

# .env.production
API_KEY=prod-api-key
DATABASE_URL=postgresql://prod-server/prod_db

# .env.test
API_KEY=test-api-key
DATABASE_URL=postgresql://localhost/test_db
```

### Validation and Sanitization

#### Input Validation
```javascript
// Validate environment variables
const requiredEnvVars = [
  'API_KEY',
  'DATABASE_URL',
  'JWT_SECRET'
];

requiredEnvVars.forEach(varName => {
  if (!process.env[varName]) {
    throw new Error(`Missing required environment variable: ${varName}`);
  }
});

// Validate API key format
const apiKeyRegex = /^[A-Za-z0-9]{32,}$/;
if (!apiKeyRegex.test(process.env.API_KEY)) {
  throw new Error('Invalid API key format');
}
```

#### Sanitization
```bash
# Sanitize environment variables
export CLEAN_API_KEY=$(echo "$API_KEY" | tr -d '\n\r')
export CLEAN_DATABASE_URL=$(echo "$DATABASE_URL" | sed 's/[^a-zA-Z0-9@:._/-]//g')
```

## Git Security

### Repository Security

#### SSH Key Setup
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your-email@domain.com"

# Add to SSH agent
ssh-add ~/.ssh/id_ed25519

# Copy public key
cat ~/.ssh/id_ed25519.pub

# Test SSH connection
ssh -T git@github.com
```

#### Git Configuration
```bash
# Configure Git user securely
git config --global user.name "Your Name"
git config --global user.email "your-email@domain.com"

# Use SSH instead of HTTPS
git config --global url."git@github.com:".insteadOf "https://github.com/"

# Enable GPG signing
git config --global commit.gpgsign true
git config --global tag.gpgsign true
```

### Secrets Detection

#### Pre-commit Hooks
```bash
# Install pre-commit
pip install pre-commit

# Create .pre-commit-config.yaml
cat > .pre-commit-config.yaml << EOF
repos:
  - repo: https://github.com/Yelp/detect-secrets
    rev: v1.4.0
    hooks:
      - id: detect-secrets
        args: ['--baseline', '.secrets.baseline']
EOF

# Install hooks
pre-commit install
```

#### Git Hooks
```bash
# Create pre-commit hook
cat > .git/hooks/pre-commit << 'EOF'
#!/bin/bash

# Check for secrets in staged files
for file in $(git diff --cached --name-only); do
  if grep -q -E "(api_key|secret|password|token)" "$file"; then
    echo "Warning: Potential secret found in $file"
    exit 1
  fi
done
EOF

chmod +x .git/hooks/pre-commit
```

### Branch Protection

#### GitHub Branch Protection
```yaml
# .github/branch-protection.yml
name: Branch Protection
on:
  push:
    branches: [ main, develop ]

jobs:
  protect:
    runs-on: ubuntu-latest
    steps:
      - name: Enable branch protection
        uses: actions/github-script@v6
        with:
          script: |
            github.rest.repos.updateBranchProtection({
              owner: context.repo.owner,
              repo: context.repo.repo,
              branch: 'main',
              required_status_checks: {
                strict: true,
                contexts: ['ci']
              },
              enforce_admins: true,
              required_pull_request_reviews: {
                required_approving_review_count: 2
              },
              restrictions: null
            })
```

## Package Security

### Dependency Scanning

#### NPM Security
```bash
# Audit dependencies
npm audit

# Fix vulnerabilities
npm audit fix

# Fix vulnerabilities (including major updates)
npm audit fix --force

# Check for outdated packages
npm outdated

# Update packages
npm update
```

#### Python Security
```bash
# Install safety
pip install safety

# Check for vulnerabilities
safety check

# Check with requirements file
safety check -r requirements.txt

# Update vulnerable packages
pip install --upgrade package-name
```

#### Automated Scanning
```yaml
# GitHub Actions security workflow
name: Security Scan
on: [push, pull_request]

jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          
      - name: Install dependencies
        run: npm ci
        
      - name: Run security audit
        run: npm audit --audit-level=moderate
        
      - name: Check for outdated packages
        run: npm outdated
```

### Package Verification

#### Integrity Checks
```bash
# Verify package integrity
npm audit

# Check package signatures
npm audit --audit-level=high

# Verify package checksums
npm ci --prefer-offline
```

#### Lock File Security
```bash
# Generate lock file
npm install --package-lock-only

# Verify lock file
npm ci

# Update lock file
npm install --package-lock-only
```

## Code Security

### Static Analysis

#### ESLint Security
```bash
# Install security plugins
npm install --save-dev eslint-plugin-security

# Configure ESLint
cat > .eslintrc.js << EOF
module.exports = {
  plugins: ['security'],
  extends: [
    'eslint:recommended',
    'plugin:security/recommended'
  ],
  rules: {
    'security/detect-object-injection': 'error',
    'security/detect-non-literal-regexp': 'error',
    'security/detect-unsafe-regex': 'error'
  }
};
EOF
```

#### SonarQube
```yaml
# .github/workflows/sonar.yml
name: SonarQube Analysis
on: [push, pull_request]

jobs:
  sonar:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
          
      - name: SonarQube Scan
        uses: sonarqube-quality-gate-action@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```

### Runtime Security

#### Input Validation
```javascript
// Validate user input
const validateInput = (input) => {
  if (typeof input !== 'string') {
    throw new Error('Input must be a string');
  }
  
  if (input.length > 1000) {
    throw new Error('Input too long');
  }
  
  // Sanitize input
  return input.replace(/[<>]/g, '');
};

// Use in API endpoints
app.post('/api/data', (req, res) => {
  try {
    const sanitizedInput = validateInput(req.body.data);
    // Process sanitized input
  } catch (error) {
    res.status(400).json({ error: error.message });
  }
});
```

#### SQL Injection Prevention
```javascript
// Use parameterized queries
const getUser = async (userId) => {
  const query = 'SELECT * FROM users WHERE id = $1';
  const result = await db.query(query, [userId]);
  return result.rows[0];
};

// Avoid string concatenation
// BAD: const query = `SELECT * FROM users WHERE id = ${userId}`;
```

## Infrastructure Security

### Cloud Security

#### AWS Security
```bash
# Configure AWS CLI securely
aws configure

# Use IAM roles instead of access keys
export AWS_PROFILE=production

# Rotate access keys regularly
aws iam create-access-key --user-name myuser
aws iam delete-access-key --user-name myuser --access-key-id OLD_KEY
```

#### Docker Security
```dockerfile
# Use non-root user
FROM node:18-alpine
RUN addgroup -g 1001 -S nodejs
RUN adduser -S nextjs -u 1001
USER nextjs

# Copy only necessary files
COPY --chown=nextjs:nodejs package*.json ./
RUN npm ci --only=production

# Don't run as root
USER 1001
```

### Network Security

#### HTTPS Configuration
```javascript
// Force HTTPS in production
if (process.env.NODE_ENV === 'production') {
  app.use((req, res, next) => {
    if (req.header('x-forwarded-proto') !== 'https') {
      res.redirect(`https://${req.header('host')}${req.url}`);
    } else {
      next();
    }
  });
}
```

#### CORS Configuration
```javascript
// Configure CORS securely
const corsOptions = {
  origin: process.env.ALLOWED_ORIGINS?.split(',') || ['http://localhost:3000'],
  credentials: true,
  optionsSuccessStatus: 200
};

app.use(cors(corsOptions));
```

## Monitoring and Alerting

### Security Monitoring

#### Log Monitoring
```javascript
// Security logging
const securityLogger = {
  logSuspiciousActivity: (activity, user, ip) => {
    console.log(`[SECURITY] Suspicious activity: ${activity} by ${user} from ${ip}`);
    // Send to security monitoring service
  },
  
  logFailedLogin: (username, ip) => {
    console.log(`[SECURITY] Failed login attempt: ${username} from ${ip}`);
  },
  
  logApiKeyUsage: (key, endpoint) => {
    console.log(`[SECURITY] API key used: ${key.substring(0, 8)}... for ${endpoint}`);
  }
};
```

#### Alerting
```yaml
# GitHub Actions security alerts
name: Security Alerts
on:
  security_advisory:
    types: [published]

jobs:
  alert:
    runs-on: ubuntu-latest
    steps:
      - name: Send Slack alert
        uses: 8398a7/action-slack@v3
        with:
          status: ${{ job.status }}
          channel: '#security'
          text: 'Security vulnerability detected!'
```

## Incident Response

### Security Incident Plan

#### Response Steps
```bash
# 1. Identify the incident
# 2. Contain the threat
# 3. Eradicate the cause
# 4. Recover systems
# 5. Document lessons learned

# Emergency response script
#!/bin/bash
# emergency-response.sh

echo "SECURITY INCIDENT DETECTED"
echo "1. Isolating affected systems..."
echo "2. Rotating all API keys..."
echo "3. Checking for unauthorized access..."
echo "4. Notifying security team..."
```

#### Recovery Procedures
```bash
# Rotate all credentials
./rotate-keys.sh

# Check for unauthorized commits
git log --oneline --since="1 day ago"

# Verify system integrity
npm audit
safety check

# Update security patches
npm update
pip install --upgrade package-name
```

## Resources

### Security Tools
- [OWASP ZAP](https://owasp.org/www-project-zap/)
- [SonarQube](https://www.sonarqube.org/)
- [Snyk](https://snyk.io/)
- [GitGuardian](https://www.gitguardian.com/)

### Documentation
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [GitHub Security](https://docs.github.com/en/github/managing-security-vulnerabilities)

### Training
- [OWASP Training](https://owasp.org/www-project-training/)
- [SANS Security Courses](https://www.sans.org/security-training/)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)

---

*Last Updated: July 27, 2025* 