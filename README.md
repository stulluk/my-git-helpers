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
- `--details`  : Show detailed commit history for each branch (last 10 commits)

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
git clone https://github.com/YOUR_USERNAME/my-git-helpers.git
cd my-git-helpers
```

2. Add scripts to your PATH:
```bash
# Option 1: Add to your PATH in ~/.bashrc or ~/.zshrc
export PATH="$PATH:$(pwd)"

# Option 2: Create symlinks in a directory already in your PATH
ln -s $(pwd)/git-active-branches ~/bin/
ln -s $(pwd)/git-find-branch-from-commit ~/bin/
```

3. Make scripts executable (if not already):
```bash
chmod +x git-active-branches git-find-branch-from-commit
```

## Requirements

- Git
- Bash
- Standard Unix utilities (date, sort, awk, etc.)

## License

MIT

