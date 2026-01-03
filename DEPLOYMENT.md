# Deploying to Vercel

This guide will help you deploy your static website to Vercel.

## Prerequisites

1. A Vercel account (sign up at [vercel.com](https://vercel.com) - free tier available)
2. Your code pushed to a Git repository (GitHub, GitLab, or Bitbucket)

## Deployment Methods

### Option 1: Deploy via Vercel CLI (Recommended for quick testing)

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm i -g vercel
   ```

2. **Login to Vercel**:
   ```bash
   vercel login
   ```

3. **Deploy from your project directory**:
   ```bash
   cd /Users/somayshsadani/Ashwagandha
   vercel
   ```

4. **Follow the prompts**:
   - Link to existing project or create new one
   - Confirm project settings
   - Deploy!

5. **For production deployment**:
   ```bash
   vercel --prod
   ```

### Option 2: Deploy via Vercel Dashboard (Recommended for production)

1. **Push your code to GitHub/GitLab/Bitbucket** (if not already done)

2. **Go to [vercel.com](https://vercel.com)** and sign in

3. **Click "Add New Project"**

4. **Import your Git repository**:
   - Select your repository from the list
   - Vercel will auto-detect it's a static site

5. **Configure project settings**:
   - **Framework Preset**: Other (or leave as default)
   - **Root Directory**: `./` (leave as default)
   - **Build Command**: Leave empty (no build needed for static HTML)
   - **Output Directory**: Leave empty (or `./`)

6. **Click "Deploy"**

7. **Your site will be live** at a URL like: `your-project-name.vercel.app`

**✅ Site is currently live at:** https://ashwagandha-one.vercel.app

## Configuration

Vercel auto-detects static sites, so no configuration file is needed. The site will automatically serve all HTML, CSS, and other static files from the repository root.

## Custom Domain (Optional)

1. Go to your project settings in Vercel dashboard
2. Navigate to "Domains"
3. Add your custom domain
4. Follow DNS configuration instructions

## Environment Variables

Not needed for this static site, but if you add any in the future:
1. Go to Project Settings → Environment Variables
2. Add your variables
3. Redeploy

## Continuous Deployment

Once connected to Git:
- Every push to `main`/`master` branch = Production deployment
- Every push to other branches = Preview deployment
- Pull requests = Preview deployment with unique URL

## Troubleshooting

- **404 errors**: Make sure all HTML files are in the root directory
- **CSS not loading**: Check that `styles.css` path is correct in HTML files
- **Build errors**: This is a static site, so there shouldn't be any. If you see errors, check `vercel.json` configuration

## Quick Commands

```bash
# Deploy to preview
vercel

# Deploy to production
vercel --prod

# View deployment logs
vercel logs

# List deployments
vercel ls
```

