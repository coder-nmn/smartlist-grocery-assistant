# 🚀 Deployment Troubleshooting Guide

## ❌ Common Vercel Deployment Error

### Error: `Environment Variable "OPENROUTER_API_KEY" references Secret "openrouter_api_key", which does not exist.`

This error occurs when the application tries to use the OpenRouter API for voice parsing, but the environment variable isn't configured in Vercel.

## ✅ Solutions

### Solution 1: Add API Key to Vercel (Recommended)

1. **Get OpenRouter API Key**
   - Go to [OpenRouter.ai](https://openrouter.ai)
   - Sign up for a free account
   - Navigate to "Keys" section
   - Create a new API key
   - Copy the key (starts with `sk-or-v1-...`)

2. **Add to Vercel Project**
   - Go to your [Vercel Dashboard](https://vercel.com/dashboard)
   - Select your SmartList project
   - Go to **Settings** → **Environment Variables**
   - Click **Add New**
   - Set:
     - **Name**: `OPENROUTER_API_KEY`
     - **Value**: Your OpenRouter API key
     - **Environment**: Production (and Preview if needed)
   - Click **Save**

3. **Redeploy**
   - Go to **Deployments** tab
   - Click **Redeploy** on the latest deployment
   - Or push a new commit to trigger automatic deployment

### Solution 2: Deploy Without AI (Quick Fix)

The app has been updated to work without the API key! It will use basic parsing instead of AI.

1. **Just Deploy**
   - The app will automatically detect missing API key
   - Voice parsing will use basic keyword matching
   - All other features work normally
   - You'll see a note: "Using basic parsing (AI not configured)"

2. **Add API Key Later**
   - You can add the API key anytime in Vercel settings
   - The app will automatically switch to AI parsing

## 🔧 Local Development Setup

1. **Create Environment File**
   ```bash
   cp .env.local.example .env.local
   ```

2. **Add Your API Key**
   ```bash
   # .env.local
   OPENROUTER_API_KEY=sk-or-v1-your-actual-key-here
   ```

3. **Test Locally**
   ```bash
   npm run dev
   ```

## 🌐 Alternative Deployment Platforms

### Netlify
1. Connect GitHub repository
2. Build command: `npm run build`
3. Publish directory: `out` or `.next`
4. Add environment variables in Site Settings

### Railway
1. Connect GitHub repository
2. Add environment variables in Variables tab
3. Automatic deployment on push

### Render
1. Connect GitHub repository
2. Build command: `npm run build`
3. Start command: `npm start`
4. Add environment variables in Environment tab

## 🧪 Testing Voice Feature

### With API Key (AI Parsing)
- Say: "Add milk, eggs, and cheese under 800 rupees"
- AI will intelligently parse items and budget
- More accurate and flexible

### Without API Key (Basic Parsing)
- Say: "Add milk eggs cheese under 800"
- Basic keyword matching
- Works for common grocery items
- Less flexible but functional

## 🔍 Debugging Tips

### Check Environment Variables
```bash
# In your Vercel project settings
OPENROUTER_API_KEY=sk-or-v1-... ✅
OPENROUTER_API_KEY=undefined ❌
```

### Check Deployment Logs
1. Go to Vercel Dashboard
2. Click on your deployment
3. Check **Function Logs** for errors
4. Look for API key related messages

### Test API Endpoint
```bash
# Test voice parsing endpoint
curl -X POST https://your-app.vercel.app/api/parse-voice \
  -H "Content-Type: application/json" \
  -d '{"transcript":"add milk and eggs"}'
```

## 📞 Support

If you're still having issues:

1. **Check the console** in browser dev tools
2. **Verify API key** is correctly set in Vercel
3. **Try redeploying** after adding environment variables
4. **Test locally first** to ensure everything works

## 🎯 Quick Deployment Checklist

- [ ] Repository pushed to GitHub
- [ ] Vercel project created and connected
- [ ] Environment variable `OPENROUTER_API_KEY` added (optional)
- [ ] Deployment successful
- [ ] Voice feature tested
- [ ] All other features working

---

**Your SmartList app should now deploy successfully!** 🎉
