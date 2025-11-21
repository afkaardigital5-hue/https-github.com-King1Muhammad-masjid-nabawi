# Masjid Nabawi - Deployment Guide

## Project Status

✅ **Fixed Issues:**
- Resolved merge conflicts in `.env` file
- Updated `nodemailer` to v7.0.10 (fixed security vulnerability)
- Verified build process works correctly
- All dependencies installed successfully
- Code committed and pushed to repository

## GitHub Repository

- **Forked Repository**: https://github.com/afkaardigital5-hue/https-github.com-King1Muhammad-masjid-nabawi
- **Branch**: main (updated with fixes)
- **Original Repository**: https://github.com/King1Muhammad/masjid-nabawi

## Development Server

The project is currently running:
- **Frontend (Vite)**: https://5173-i53700s7o6vetr5dqm3in-82b888ba.sandbox.novita.ai
- **Note**: Backend server has a cyclic dependency issue that needs to be resolved for full functionality

## Deployment Options

### Option 1: Vercel (Recommended)

1. **Prerequisites**:
   - Create a Vercel account at https://vercel.com
   - Connect your GitHub repository

2. **Deploy via Vercel Dashboard**:
   ```bash
   # Go to https://vercel.com/new
   # Import your GitHub repository
   # Configure environment variables (see below)
   # Deploy!
   ```

3. **Deploy via CLI**:
   ```bash
   # Install Vercel CLI
   npm install -g vercel
   
   # Login to Vercel
   vercel login
   
   # Deploy to production
   vercel --prod
   ```

### Option 2: Netlify

1. **Prerequisites**:
   - Create a Netlify account at https://netlify.com
   - Connect your GitHub repository

2. **Deploy via Netlify Dashboard**:
   - Go to https://app.netlify.com/start
   - Import your GitHub repository
   - Build settings are already configured in `netlify.toml`
   - Add environment variables
   - Deploy!

3. **Deploy via CLI**:
   ```bash
   # Install Netlify CLI
   npm install -g netlify-cli
   
   # Login to Netlify
   netlify login
   
   # Deploy
   netlify deploy --prod
   ```

## Required Environment Variables

Configure these in your deployment platform:

```env
# Database Configuration
DATABASE_URL=postgresql://neondb_owner:npg_WdKeR60mhlIC@ep-still-term-a87enoey-pooler.eastus2.azure.neon.tech/neondb?sslmode=require

# Session Secret
SESSION_SECRET=masjid_nabawi_secret_key_2024

# Node Environment
NODE_ENV=production

# Email Configuration
EMAIL_USER=jamiamasjidnabviqureshihashmi@gmail.com
EMAIL_PASSWORD=ejis hhrl ymej jsew
EMAIL_FROM=Masjid-e-Nabawi Islamabad <jamiamasjidnabviqureshihashmi@gmail.com>
EMAIL_ADMIN=jamiamasjidnabviqureshihashmi@gmail.com

# Stripe (if using payments)
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

# JWT Secret
JWT_SECRET=your_jwt_secret
```

## Build Configuration

The project is configured to build automatically:

- **Build Command**: `npm run build`
- **Output Directory**: `dist/public`
- **Node Version**: 18.x or higher

## Post-Deployment Steps

1. **Database Setup**:
   ```bash
   npm run db:push
   ```

2. **Verify Deployment**:
   - Test prayer times functionality
   - Test donation form
   - Test contact form
   - Test madrasa enrollment

3. **Monitor**:
   - Check deployment logs
   - Monitor error reports
   - Test all API endpoints

## Known Issues

1. **Server Cyclic Dependency**: 
   - The server has a cyclic module dependency issue
   - This may need to be fixed for full backend functionality
   - Frontend builds and runs successfully

2. **Security Warnings**:
   - Some dev dependencies have security vulnerabilities
   - These are mostly in `netlify-cli` and don't affect production
   - Consider updating dev dependencies periodically

## Additional Resources

- **Vercel Documentation**: https://vercel.com/docs
- **Netlify Documentation**: https://docs.netlify.com
- **Project README**: See `README.md` for feature details

## Support

For issues or questions:
- Check GitHub issues
- Review deployment logs
- Contact project maintainer

---

**Last Updated**: 2025-11-21
**Status**: Ready for deployment
