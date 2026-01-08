# Publishing to GitHub Pages

This guide explains how to publish your Tensil landing page using GitHub Pages.

## What I've Set Up

I've created a GitHub Actions workflow (`.github/workflows/deploy.yml`) that will automatically:
1. Build your Hugo site whenever you push to the `master` or `main` branch
2. Deploy it to GitHub Pages

## Steps to Publish

### 1. Push the Workflow to GitHub

```bash
git add .github/workflows/deploy.yml
git commit -m "Add GitHub Pages deployment workflow"
git push origin master
```

### 2. Enable GitHub Pages in Your Repository

1. Go to your repository: https://github.com/ankur-gupta-29/tensil-landing
2. Click on **Settings** (top menu)
3. In the left sidebar, click **Pages** (under "Code and automation")
4. Under **Source**, select **GitHub Actions**
5. Save the settings

### 3. Trigger the Deployment

The workflow will automatically run when you push to the `master` branch. You can also:
- Go to the **Actions** tab in your GitHub repository
- Click on the "Deploy Hugo site to GitHub Pages" workflow
- Click **Run workflow** to manually trigger it

### 4. Access Your Published Site

Once the workflow completes (usually takes 1-2 minutes), your site will be available at:

**https://ankur-gupta-29.github.io/tensil-landing/**

## Monitoring Deployments

- Go to the **Actions** tab to see the build and deployment status
- Each push to `master` will automatically trigger a new deployment
- You'll see a green checkmark ✓ when deployment succeeds

## Troubleshooting

If the deployment fails:
1. Check the **Actions** tab for error messages
2. Ensure all Git submodules are properly initialized
3. Verify that `config.toml` has the correct `baseURL` setting

## Custom Domain (Optional)

To use a custom domain:
1. Add a `CNAME` file to the `static/` directory with your domain name
2. Configure your DNS provider to point to GitHub Pages
3. Update the custom domain in GitHub Pages settings

## Notes

- The workflow uses Hugo Extended version 0.128.0
- It automatically handles submodules (like the Docsy theme)
- The site is built with `--gc` and `--minify` flags for optimization
