# GitHub Workflows Configuration

## Available Workflows

### 1. Profile Update
- **File**: `profile-update.yml`
- **Triggers**: Daily (00:00 UTC), Push to main/master
- **Purpose**: Automatically updates profile README and maintenance logs
- **Permissions**: Write access to repository

### 2. Code Quality Check
- **File**: `code-quality.yml`
- **Triggers**: Push/PR to main/master/develop
- **Purpose**: Runs linting, formatting checks with Python 3.9, 3.10, 3.11
- **Tools Used**:
  - Black (code formatting)
  - isort (import sorting)
  - flake8 (style guide enforcement)
  - pylint (code analysis)

### 3. GitHub Stats Sync
- **File**: `sync-stats.yml`
- **Triggers**: Weekly (Sunday 00:00), Push to main/master
- **Purpose**: Syncs and logs GitHub statistics
- **Data Tracked**:
  - Public repositories count
  - Followers/Following
  - Account creation date
  - Last sync timestamp

### 4. README Validation
- **File**: `readme-validate.yml`
- **Triggers**: README.md changes
- **Purpose**: Validates markdown syntax and checks badge URLs
- **Checks**:
  - Markdown linting with .markdownlint.json
  - Link validation
  - Badge URL status codes

### 5. Contribution Tracking
- **File**: `contributions.yml`
- **Triggers**: Every 6 hours
- **Purpose**: Generates contribution tracking reports
- **Output**: `CONTRIBUTIONS.md`

## Setup Instructions

1. Push this repository to GitHub
2. Enable GitHub Actions in repository settings
3. Ensure `GITHUB_TOKEN` has write permissions
4. Workflows will automatically run based on triggers

## Customization

### Change Schedule Times
Edit the `cron` expression in workflow files:
- `0 0 * * *` = Daily at 00:00 UTC
- `0 0 * * 0` = Weekly on Sunday at 00:00 UTC
- `0 */6 * * *` = Every 6 hours

### Disable a Workflow
Remove the `.yml` file or set `schedule` to empty

### Add Custom Triggers
Modify the `on:` section in workflow files

## Monitoring

Check workflow runs in: **Settings → Actions → All workflows**

## Troubleshooting

- If workflows don't run, ensure Actions are enabled
- Check commit permissions for the bot user
- Verify `[skip ci]` tags in commit messages to skip runs

---

**Last Updated**: 2024
