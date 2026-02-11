# SPARC Newsletter Workflow
## Simple Bloomerang Link Method

---

## How It Works

When you send a newsletter through Bloomerang, it creates a web-hosted version with a "View in Browser" link. You simply copy that URL and add it to your website's newsletter page.

**Total time:** ~2 minutes per newsletter

---

## Step-by-Step Process

### 1. Send Newsletter from Bloomerang
- Create and send your newsletter as usual
- Include "Newsletter" in the subject line for consistency

### 2. Get the "View in Browser" URL
- Open the sent email (check your sent folder or send yourself a copy)
- Click the **"View in Browser"** or **"View this email in your browser"** link at the top
- **Copy the URL** from your browser's address bar

The URL will look something like:
```
https://crm.bloomerang.co/HostedEmail/...
```

### 3. Update the Newsletter Page

Edit `/website/newsletter/index.html`

Find the `newsletters-grid` section (around line 435) and add a new card at the **TOP**:

```html
<div class="newsletter-card">
    <div class="newsletter-card-header">
        <h3>February 2026</h3>
        <span>Monthly Update</span>
    </div>
    <div class="newsletter-card-body">
        <ul>
            <li>Highlight from newsletter</li>
            <li>Another highlight</li>
            <li>Third highlight</li>
        </ul>
        <a href="PASTE_BLOOMERANG_URL_HERE" target="_blank">
            Read Newsletter
            <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
        </a>
    </div>
</div>
```

Replace `PASTE_BLOOMERANG_URL_HERE` with the URL you copied.

### 4. Publish
```bash
git add newsletter/index.html
git commit -m "Add February 2026 newsletter"
git push
```

---

## Quick Checklist

When you send a newsletter:

- [ ] Send newsletter from Bloomerang
- [ ] Open email → Click "View in Browser"
- [ ] Copy the URL from browser
- [ ] Edit `/newsletter/index.html` - add new card with URL
- [ ] Git commit and push
- [ ] Verify at: sparcsolutions.org/newsletter/

---

## Tips

1. **Save URLs in a spreadsheet** - Keep a list of all newsletter URLs for reference
2. **Consistent naming** - Use month/year in card headers
3. **Add highlights** - Include 2-3 bullet points of what's in each newsletter
4. **Keep recent only** - Show the 6 most recent newsletters, archive older ones

---

## Email Filter (Optional)

To keep newsletter copies organized in Gmail:

1. Gmail → Search options (▼ in search bar)
2. Subject: `Newsletter`
3. Create filter → Apply label: `SPARC Newsletter`

This makes it easy to find past newsletters when you need the URLs.
