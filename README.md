# Git Helpers

A collection of useful git helper scripts to make your git workflow more efficient.

## Scripts

### git-active-branches

List branches that have received commits within a specified time period.

**Usage:**
```bash
git-active-branches [--months=N] [--details]
```

**Options:**
- `--months=N` : Show branches with commits in the last N months (default: 6)
- `--details`  : Show detailed commit history for each branch (last 10 commits with date, SHA, author, and subject)

**Examples:**
```bash
# List branches with commits in the last 6 months
git-active-branches

# List branches with commits in the last 12 months
git-active-branches --months 12

# Show detailed commit history
git-active-branches --details

# Combine options
git-active-branches --months 12 --details
```

### git-find-branch-from-commit

Find all branches that contain a specific commit.

**Usage:**
```bash
git-find-branch-from-commit <commit-sha>
```

**Arguments:**
- `<commit-sha>` : The commit SHA to search for (minimum 8 characters)

**Examples:**
```bash
# Find branches containing a commit
git-find-branch-from-commit abc12345

# Using full SHA
git-find-branch-from-commit abc1234567890def
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/stulluk/my-git-helpers.git
cd my-git-helpers
```

2. Install scripts (choose one method):

**Option 1: Copy to /usr/bin (system-wide, requires sudo):**
```bash
sudo cp git-active-branches git-find-branch-from-commit /usr/bin/
sudo chmod +x /usr/bin/git-active-branches /usr/bin/git-find-branch-from-commit
```

**Option 2: Add to your PATH:**
```bash
# Add to your PATH in ~/.bashrc or ~/.zshrc
export PATH="$PATH:$(pwd)"
```

**Option 3: Create symlinks in a directory already in your PATH:**
```bash
ln -s $(pwd)/git-active-branches ~/bin/
ln -s $(pwd)/git-find-branch-from-commit ~/bin/
```

3. (Optional) Enable bash completion:
```bash
# Add to your ~/.bashrc for persistent completion
source /usr/bin/git-active-branches 2>/dev/null
source /usr/bin/git-find-branch-from-commit 2>/dev/null
```

Note: Scripts are already executable, but if needed:
```bash
chmod +x git-active-branches git-find-branch-from-commit
```

## Requirements

- Git
- Bash
- Standard Unix utilities (date, sort, awk, etc.)

## License

MIT

