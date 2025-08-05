# Mock User Data - Templates and Examples

This folder contains **template files and example data** to demonstrate the Fitness Guide file structure and format.

## ⚠️ Important: Personal Setup Required

**This is NOT your personal fitness data!** These are templates and examples.

### To Set Up for Personal Use:

1. **Keep this folder as-is** (it provides templates and examples)
2. **Create a new folder**: `User Data/` (parallel to this folder)
3. **Copy templates**: Use files from here as starting points for your personal data
4. **Add to .gitignore**: Ensure `User Data/` is in your `.gitignore` file

### File Structure Reference:

```
Fitness Guide/
├── Mock User Data/          ← Templates (safe to commit)
│   ├── Profile.md          ← Example profile
│   ├── PRs/               ← Example PR files
│   └── [example files...]
│
└── User Data/              ← Your personal data (add to .gitignore!)
    ├── Profile.md          ← Your actual profile
    ├── PRs/               ← Your actual PRs
    └── [your files...]
```

## Template Files Included:

- **Profile.md**: Example user profile with goals and settings
- **PRs/**: Example personal record files with proper formatting
- **Logs/**: Example workout, nutrition, and recovery logs
- **Tracking/**: Example body metrics and progress tracking
- **Current_Programs/**: Example training program files

## Privacy & Security:

- **Mock User Data/**: Safe to commit to version control
- **User Data/**: Should NEVER be committed (contains personal information)
- **Always check**: Ensure your `.gitignore` includes `User Data/`

These templates show the correct file formats and data structures the Fitness Guide system expects. Use them as references when creating your personal fitness tracking files.