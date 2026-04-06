# Analytics Setup Guide

This project includes support for multiple analytics tools to help you track page views and user behavior.

## Available Analytics Tools

### 1. Google Analytics 4 (GA4) ✅ Currently Active
- **Status**: Already configured with ID `G-GBVBTHC8QT`
- **Features**: Page views, user behavior, traffic sources, conversions
- **Setup**:
  1. Go to [Google Analytics](https://analytics.google.com/)
  2. Create a property or use existing one
  3. Get your Measurement ID (format: `G-XXXXXXXXXX`)
  4. Set environment variable: `PUBLIC_GA_MEASUREMENT_ID=G-XXXXXXXXXX`

### 2. Microsoft Clarity (Recommended)
- **Status**: Not yet configured
- **Features**:
  - Free heatmaps showing where users click and scroll
  - Session recordings to see how users interact with your site
  - User insights and behavior analytics
- **Setup**:
  1. Go to [Microsoft Clarity](https://clarity.microsoft.com/)
  2. Sign up with your Microsoft account (free)
  3. Create a new project for your website
  4. Copy your Clarity Project ID
  5. Set environment variable: `PUBLIC_MICROSOFT_CLARITY_ID=your-project-id`

### 3. Cloudflare Web Analytics (Privacy-Focused)
- **Status**: Not yet configured
- **Features**:
  - Privacy-focused analytics (GDPR compliant)
  - No cookies required
  - Free tier available
  - Real-time visitor statistics
- **Setup**:
  1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
  2. Navigate to Web Analytics
  3. Add your site and get your token
  4. Set environment variable: `PUBLIC_CF_WEB_ANALYTICS_TOKEN=your-token`

## Configuration

### Using Environment Variables

Create a `.env` file in the root of your project with:

```env
# Google Analytics 4 (GA4) Measurement ID
PUBLIC_GA_MEASUREMENT_ID=G-GBVBTHC8QT

# Microsoft Clarity Project ID
PUBLIC_MICROSOFT_CLARITY_ID=your-clarity-id

# Cloudflare Web Analytics Token
PUBLIC_CF_WEB_ANALYTICS_TOKEN=your-cloudflare-token
```

### Default Behavior

- Google Analytics is enabled by default with the existing ID
- Microsoft Clarity and Cloudflare Analytics are disabled until you add their IDs
- All analytics tools are conditionally loaded (only if their IDs are provided)

## Viewing Analytics

- **Google Analytics**: Visit [analytics.google.com](https://analytics.google.com/)
- **Microsoft Clarity**: Visit [clarity.microsoft.com](https://clarity.microsoft.com/)
- **Cloudflare Analytics**: Visit your [Cloudflare Dashboard](https://dash.cloudflare.com/)

## Privacy Considerations

- Google Analytics: Uses cookies, requires cookie consent in some regions (GDPR)
- Microsoft Clarity: Uses cookies for session recordings
- Cloudflare Web Analytics: Privacy-focused, no cookies required

## Recommendations

1. **Start with Google Analytics** - Already set up, provides comprehensive analytics
2. **Add Microsoft Clarity** - Great for understanding user behavior with heatmaps
3. **Consider Cloudflare Analytics** - If you want a privacy-focused alternative

All three tools can run simultaneously without conflicts.
