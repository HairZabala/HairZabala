# Setup Instructions for Private Repository Stats

## Step 1: Create a GitHub Personal Access Token

1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Or visit: https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Give it a name like "GitHub Profile Stats"
4. Select the `repo` scope (this allows access to private repository data)
5. Click "Generate token"
6. **Copy the token immediately** (you won't see it again!)

## Step 2: Add Token to Repository Secrets

1. Go to your repository on GitHub (the one with your profile README)
2. Navigate to: Settings → Secrets and variables → Actions
3. Click "New repository secret"
4. Name: `GH_TOKEN`
5. Value: Paste your personal access token
6. Click "Add secret"

## Step 3: Enable GitHub Actions

1. Go to your repository Settings → Actions → General
2. Make sure "Allow all actions and reusable workflows" is enabled
3. Save changes

## Step 4: Trigger the Workflow

1. Go to your repository → Actions tab
2. Find the "Update GitHub Stats with Private Repos" workflow
3. Click "Run workflow" → "Run workflow" (this will generate the stats images)
4. Wait for it to complete (should take ~30 seconds)

## Step 5: Verify It's Working

1. After the workflow runs, check that the `stats/` directory was created
2. Verify it contains `github-stats.svg` and `top-langs.svg`
3. Your README should now display stats including private repositories!

## Notes

- The workflow runs automatically every 6 hours to keep stats updated
- You can manually trigger it anytime from the Actions tab
- The stats images are stored in your repository (in the `stats/` folder)
- Private repository data will only be visible to you (via the authenticated API)
