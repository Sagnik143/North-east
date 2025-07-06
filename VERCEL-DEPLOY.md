# Deploy North East Explorer on Vercel (FREE)

This guide will help you deploy your North East Explorer application on Vercel's free tier in just a few minutes.

## Prerequisites

1. **GitHub Account** (free) - github.com
2. **Vercel Account** (free) - vercel.com
3. **Neon Database** (free) - neon.tech
4. **OpenAI API Key** - platform.openai.com

## Step 1: Get Your Database URL (FREE)

1. Go to [neon.tech](https://neon.tech)
2. Sign up with GitHub (it's free)
3. Create a new project called "northeast-explorer"
4. Copy the connection string (looks like: `postgresql://username:password@host/database`)

## Step 2: Get OpenAI API Key

1. Go to [platform.openai.com](https://platform.openai.com)
2. Sign up and add payment method (you get $5 free credits)
3. Go to API Keys section
4. Create new key and copy it (starts with `sk-`)

## Step 3: Upload to GitHub

### Option A: Upload Files Directly
1. Go to [github.com](https://github.com) and create new repository
2. Name it "northeast-explorer" 
3. Upload all files from the zip package
4. Make sure to include the `api/` folder and `vercel.json`

### Option B: Use GitHub Desktop (Easier)
1. Download GitHub Desktop
2. Create new repository locally
3. Extract zip files into the repository folder
4. Commit and push to GitHub

## Step 4: Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) and sign up with GitHub
2. Click "New Project"
3. Import your "northeast-explorer" repository
4. **IMPORTANT**: Before deploying, add environment variables:
   - Click "Environment Variables"
   - Add `DATABASE_URL` = your Neon database URL
   - Add `OPENAI_API_KEY` = your OpenAI API key
5. Click "Deploy"

Vercel will automatically:
- Build your React frontend
- Set up serverless functions for your API
- Give you a free domain like `northeast-explorer.vercel.app`

## Step 5: Test Your Deployment

After deployment (takes 2-3 minutes):
1. Visit your Vercel URL
2. Check that all 8 North East states appear
3. Test the AI recommendations feature
4. Verify booking functionality works

## Vercel Free Tier Limits

✅ **What's Included FREE:**
- 100GB bandwidth per month
- 100 serverless function executions per day
- Automatic HTTPS
- Global CDN
- Custom domain support

⚠️ **Limitations:**
- 10-second serverless function timeout
- 1000 build minutes per month
- Functions sleep when not used (cold starts)

## File Structure for Vercel

Your repository should look like:
```
├── api/                    # Serverless functions
│   ├── states.ts          # /api/states endpoint
│   ├── destinations.ts    # /api/destinations endpoint
│   ├── accommodations.ts  # /api/accommodations endpoint
│   ├── transport.ts       # /api/transport endpoint
│   ├── ai-recommendations.ts # /api/ai-recommendations
│   ├── ai-itinerary.ts    # /api/ai-itinerary
│   ├── itineraries.ts     # /api/itineraries endpoint
│   └── bookings.ts        # /api/bookings endpoint
├── client/                # React frontend
├── server/                # Shared backend logic
├── shared/                # Database schema
├── vercel.json            # Vercel configuration
└── package.json           # Dependencies
```

## Troubleshooting

**"Function timeout" errors:**
- This happens with complex AI requests
- The free tier has 10-second limit
- Consider upgrading to Pro ($20/month) for 60-second timeout

**"Database connection failed":**
- Verify your DATABASE_URL is correct
- Check Neon database is active
- Ensure connection string includes password

**"OpenAI API errors":**
- Verify API key is correct
- Check you have credits at platform.openai.com/usage
- Ensure API key has proper permissions

**Build errors:**
- Make sure all files are uploaded to GitHub
- Check package.json exists
- Verify api/ folder structure is correct

## Custom Domain (Optional)

Once deployed, you can add a custom domain:
1. Go to your Vercel project settings
2. Click "Domains"
3. Add your domain (like yourdomain.com)
4. Update DNS settings as instructed

## Monitoring

Vercel provides:
- Real-time function logs
- Performance analytics
- Error tracking
- Deployment history

Access these in your Vercel dashboard.

## Updating Your App

To update your deployed app:
1. Make changes to your GitHub repository
2. Push changes to GitHub
3. Vercel automatically redeploys

That's it! Your North East Explorer will be live on the internet with a free Vercel domain.