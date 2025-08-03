# NPM Setup Guide

A comprehensive guide to setting up and using npm (Node Package Manager) for JavaScript/Node.js development, including essential commands and best practices.

## Overview

npm is the default package manager for Node.js, allowing you to install, manage, and share JavaScript packages and dependencies.

## Installation

### Prerequisites
- Node.js (npm comes bundled with Node.js)
- Internet connection for downloading packages

### Step 1: Install Node.js and npm
```bash
# macOS (using Homebrew)
brew install node

# Ubuntu/Debian
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs

# Windows
# Download from https://nodejs.org/
```

### Step 2: Verify Installation
```bash
node --version
npm --version
```

### Step 3: Configure npm
```bash
# Set default author
npm config set init.author.name "Your Name"
npm config set init.author.email "your-email@domain.com"

# Set default license
npm config set init.license "MIT"

# Set default repository
npm config set init.repository.url "https://github.com/username/repo"
```

## Essential Commands

### Project Initialization

#### Create New Project
```bash
# Initialize new project
npm init

# Initialize with default values
npm init -y

# Initialize with specific package name
npm init my-package-name
```

#### package.json Structure
```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "A brief description of your project",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node index.js",
    "dev": "nodemon index.js",
    "build": "webpack --mode production"
  },
  "keywords": ["node", "javascript", "web"],
  "author": "Your Name <your-email@domain.com>",
  "license": "MIT",
  "dependencies": {
    "express": "^4.18.2"
  },
  "devDependencies": {
    "nodemon": "^3.0.1"
  }
}
```

### Package Management

#### Installing Packages
```bash
# Install package as dependency
npm install express
npm i express

# Install package as dev dependency
npm install --save-dev nodemon
npm i -D nodemon

# Install package globally
npm install -g create-react-app
npm i -g create-react-app

# Install specific version
npm install express@4.18.2

# Install latest version
npm install express@latest
```

#### Removing Packages
```bash
# Remove package
npm uninstall express
npm un express

# Remove global package
npm uninstall -g create-react-app
npm un -g create-react-app

# Remove dev dependency
npm uninstall --save-dev nodemon
npm un -D nodemon
```

#### Updating Packages
```bash
# Update all packages
npm update

# Update specific package
npm update express

# Update global packages
npm update -g

# Check outdated packages
npm outdated

# Update to latest versions (including major versions)
npx npm-check-updates -u
npm install
```

### Scripts and Automation

#### Running Scripts
```bash
# Run script defined in package.json
npm run start
npm start

# Run test script
npm test
npm run test

# Run custom script
npm run build
npm run dev

# Run script with arguments
npm run build -- --mode production
```

#### Common Scripts
```json
{
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "build": "webpack --mode production",
    "test": "jest",
    "test:watch": "jest --watch",
    "lint": "eslint .",
    "lint:fix": "eslint . --fix",
    "format": "prettier --write .",
    "clean": "rm -rf dist node_modules",
    "preinstall": "node check-node-version.js",
    "postinstall": "echo 'Installation complete!'"
  }
}
```

### Dependency Management

#### Understanding Dependencies
```bash
# Production dependencies (required for runtime)
npm install express

# Development dependencies (required for development only)
npm install --save-dev jest

# Peer dependencies (required by the package but not installed)
npm install --save-peer react

# Optional dependencies (not required but enhance functionality)
npm install --save-optional fsevents
```

#### Lock Files
```bash
# Generate package-lock.json
npm install

# Install from package-lock.json
npm ci

# Update lock file
npm install --package-lock-only
```

#### Dependency Analysis
```bash
# View dependency tree
npm ls

# View dependency tree for specific package
npm ls express

# Check for security vulnerabilities
npm audit

# Fix security vulnerabilities
npm audit fix

# Fix security vulnerabilities (including major updates)
npm audit fix --force
```

## Advanced Commands

### Publishing Packages

#### Prepare for Publishing
```bash
# Login to npm registry
npm login

# Check if package name is available
npm search package-name

# Set package visibility
npm config set access public
npm config set access restricted
```

#### Publishing
```bash
# Publish package
npm publish

# Publish with specific tag
npm publish --tag beta

# Unpublish package (within 72 hours)
npm unpublish package-name

# Deprecate package
npm deprecate package-name "This package is deprecated"
```

### Workspaces and Monorepos

#### Setup Workspaces
```json
{
  "name": "my-monorepo",
  "private": true,
  "workspaces": [
    "packages/*",
    "apps/*"
  ]
}
```

#### Workspace Commands
```bash
# Install dependencies in all workspaces
npm install

# Run script in all workspaces
npm run build --workspaces

# Run script in specific workspace
npm run build --workspace=packages/my-package

# Add dependency to specific workspace
npm install express --workspace=packages/my-package
```

### Configuration

#### npmrc Configuration
```bash
# Create .npmrc file
cat > .npmrc << EOF
registry=https://registry.npmjs.org/
save-exact=true
package-lock=true
audit=false
fund=false
EOF
```

#### Environment-Specific Config
```bash
# Set registry for scoped packages
npm config set @myorg:registry https://npm.myorg.com

# Set authentication token
npm config set //registry.npmjs.org/:_authToken=your-token

# Set proxy settings
npm config set proxy http://proxy.company.com:8080
npm config set https-proxy http://proxy.company.com:8080
```

## Best Practices

### Package.json Best Practices

#### Essential Fields
```json
{
  "name": "my-package",
  "version": "1.0.0",
  "description": "Clear description of what the package does",
  "main": "index.js",
  "files": [
    "index.js",
    "lib/",
    "dist/"
  ],
  "scripts": {
    "start": "node index.js",
    "test": "jest",
    "build": "webpack"
  },
  "keywords": ["relevant", "keywords"],
  "author": "Your Name <email@domain.com>",
  "license": "MIT",
  "repository": {
    "type": "git",
    "url": "https://github.com/username/repo.git"
  },
  "bugs": {
    "url": "https://github.com/username/repo/issues"
  },
  "homepage": "https://github.com/username/repo#readme"
}
```

#### Version Management
```bash
# Semantic versioning
npm version patch  # 1.0.0 -> 1.0.1
npm version minor  # 1.0.0 -> 1.1.0
npm version major  # 1.0.0 -> 2.0.0

# Pre-release versions
npm version prerelease --preid=alpha  # 1.0.0 -> 1.0.0-alpha.0
npm version prerelease --preid=beta   # 1.0.0-alpha.0 -> 1.0.0-beta.0
```

### Security Best Practices

#### Dependency Security
```bash
# Regular security audits
npm audit

# Use npm ci for CI/CD
npm ci

# Lock dependency versions
npm install --save-exact

# Use .npmrc for security settings
echo "audit=false" >> .npmrc
echo "fund=false" >> .npmrc
```

#### Package Security
```bash
# Verify package integrity
npm audit

# Use trusted packages
npm install --audit

# Check package popularity and maintenance
npm view package-name
```

## Troubleshooting

### Common Issues

#### Installation Problems
```bash
# Clear npm cache
npm cache clean --force

# Delete node_modules and reinstall
rm -rf node_modules package-lock.json
npm install

# Check npm configuration
npm config list

# Reset npm configuration
npm config set registry https://registry.npmjs.org/
```

#### Permission Issues
```bash
# Fix global package permissions
sudo chown -R $USER /usr/local/lib/node_modules

# Use nvm for Node.js version management
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install node
nvm use node
```

#### Network Issues
```bash
# Set npm registry
npm config set registry https://registry.npmjs.org/

# Use different DNS
npm config set registry http://registry.npmjs.org/

# Check network connectivity
npm ping
```

### Performance Optimization

#### Faster Installations
```bash
# Use npm ci for faster installs
npm ci

# Use npm cache
npm cache verify

# Use parallel installations
npm install --prefer-offline
```

#### Bundle Size Optimization
```bash
# Analyze bundle size
npm install -g webpack-bundle-analyzer
webpack-bundle-analyzer bundle.js

# Use tree shaking
npm install --save-dev webpack
```

## Useful Aliases and Shortcuts

### npm Aliases
```bash
# Common aliases
npm i    # npm install
npm un   # npm uninstall
npm up   # npm update
npm t    # npm test
npm run  # npm run
npm ls   # npm list
npm ln   # npm link
npm ln   # npm link
```

### Custom Scripts
```json
{
  "scripts": {
    "dev": "nodemon index.js",
    "start": "node index.js",
    "build": "webpack --mode production",
    "test": "jest",
    "test:watch": "jest --watch",
    "lint": "eslint .",
    "lint:fix": "eslint . --fix",
    "format": "prettier --write .",
    "clean": "rm -rf dist node_modules",
    "reset": "rm -rf node_modules package-lock.json && npm install"
  }
}
```

## Resources

### Documentation
- [npm Documentation](https://docs.npmjs.com/)
- [Node.js Documentation](https://nodejs.org/docs/)
- [package.json Reference](https://docs.npmjs.com/cli/v8/configuring-npm/package-json)

### Community
- [npm Community](https://www.npmjs.com/support)
- [Stack Overflow npm](https://stackoverflow.com/questions/tagged/npm)
- [Reddit r/node](https://reddit.com/r/node)

### Tools
- [npm-check-updates](https://github.com/tjunnone/npm-check-updates)
- [npm-audit-resolver](https://github.com/IBM/npm-audit-resolver)
- [npm-why](https://github.com/amio/npm-why)

---

*Last Updated: July 27, 2025* 