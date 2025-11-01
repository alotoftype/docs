# Setting Up Algolia DocSearch

This guide will help you configure Algolia DocSearch for the Voiden documentation site.

## 📋 What is Algolia DocSearch?

Algolia DocSearch is a free search service for documentation websites. It provides:
- ⚡ Lightning-fast search
- 🎯 Relevant, ranked results
- 📱 Mobile-responsive search UI
- 🔍 Keyboard shortcuts (Cmd/Ctrl + K)

## 🚀 Getting Started

### Step 1: Apply for DocSearch

1. Visit [Algolia DocSearch Apply](https://docsearch.algolia.com/apply/)
2. Fill out the application form:
   - **URL**: Your deployed documentation URL (e.g., `https://docs.voiden.com`)
   - **Email**: Your contact email
   - **Repository**: Link to your GitHub repository
3. Submit the application

**Requirements:**
- Your documentation must be publicly available
- You must be the owner/maintainer of the site
- The content must be technical documentation (not marketing)

### Step 2: Wait for Approval

- Algolia typically responds within a few days
- They'll send you an email with your API credentials
- You'll receive:
  - `appId` - Your application ID
  - `apiKey` - Your search-only API key (safe to commit)
  - `indexName` - Your index name (usually your project name)

### Step 3: Configure Docusaurus

Once you receive your credentials, update `docusaurus.config.ts`:

```typescript
algolia: {
  appId: 'YOUR_APP_ID',           // Replace with your actual App ID
  apiKey: 'YOUR_SEARCH_API_KEY',   // Replace with your actual API Key
  indexName: 'voiden',             // Replace if different
  contextualSearch: true,
  searchParameters: {},
  searchPagePath: false,           // Set to 'search' if you want a dedicated search page
},
```

### Step 4: Test Search

1. Start your dev server: `npm start`
2. Look for the search icon/bar in the navbar
3. Try searching for documentation terms
4. Press `Cmd/Ctrl + K` to open search with keyboard

## 🔧 Configuration Options

### Basic Configuration

```typescript
algolia: {
  appId: 'BH4D9OD16A',
  apiKey: '25626fae796133dc1e734c6bcaaeac3c',
  indexName: 'voiden',
}
```

### Advanced Configuration

```typescript
algolia: {
  appId: 'BH4D9OD16A',
  apiKey: '25626fae796133dc1e734c6bcaaeac3c',
  indexName: 'voiden',

  // Optional: Search across different doc versions
  contextualSearch: true,

  // Optional: Custom Algolia search parameters
  searchParameters: {
    facetFilters: ['language:en', 'version:1.0'],
  },

  // Optional: Enable dedicated search results page
  searchPagePath: 'search',

  // Optional: Custom placeholder text
  placeholder: 'Search docs...',

  // Optional: Custom translations
  translations: {
    button: {
      buttonText: 'Search',
      buttonAriaLabel: 'Search',
    },
  },
}
```

## 🎨 Customizing Search Appearance

The search UI inherits your site's theme colors automatically. To customize further, add CSS to `src/css/custom.css`:

```css
/* Customize search button */
.DocSearch-Button {
  border-radius: 8px;
  background: var(--ifm-background-surface-color);
}

/* Customize search modal */
.DocSearch-Modal {
  /* Your custom styles */
}

/* Customize search results */
.DocSearch-Hit {
  /* Your custom styles */
}
```

## 🔄 How Algolia Updates Your Index

After configuration, Algolia will:
1. **Crawl your site** regularly (usually once per week)
2. **Index your content** automatically
3. **Update search results** as your docs change

You don't need to manually trigger crawls - Algolia handles this for you.

## 🐛 Troubleshooting

### Search bar not appearing?

- Verify your API credentials are correct
- Check browser console for errors
- Ensure the `algolia` config is in `themeConfig` section
- Try clearing `.docusaurus` cache: `npm run clear`

### No search results?

- Wait 24-48 hours after initial setup for first crawl
- Verify your site is publicly accessible
- Check that Algolia has successfully crawled your site (they'll email you)
- Ensure your content has proper HTML structure

### Search results are outdated?

- Algolia crawls weekly by default
- Request a manual crawl by contacting Algolia support
- Check crawl schedule in your Algolia dashboard

## 📚 Additional Resources

- [Algolia DocSearch Documentation](https://docsearch.algolia.com/docs/what-is-docsearch)
- [Docusaurus Search Docs](https://docusaurus.io/docs/search)
- [Algolia Dashboard](https://www.algolia.com/dashboard)

## 🔐 Security Note

The `apiKey` provided by Algolia is a **search-only** key that:
- ✅ Can be safely committed to your repository
- ✅ Only allows read access to search
- ❌ Cannot modify your index
- ❌ Cannot access admin functions

## 💡 Alternative: Self-Hosted Search

If you prefer not to use Algolia, consider these alternatives:

1. **Local Search Plugin**: `@easyops-cn/docusaurus-search-local`
   - No external dependencies
   - Works offline
   - Limited features

2. **Typesense**: Open-source alternative to Algolia
   - Self-hosted
   - More control
   - Requires setup

## ✅ Checklist

Before going live with search:

- [ ] Applied for Algolia DocSearch
- [ ] Received API credentials from Algolia
- [ ] Updated `docusaurus.config.ts` with credentials
- [ ] Tested search locally
- [ ] Deployed site
- [ ] Verified Algolia has crawled the deployed site
- [ ] Search returns relevant results

---

Need help? Open an issue on [GitHub](https://github.com/VoidenHQ/feedback/issues)!
