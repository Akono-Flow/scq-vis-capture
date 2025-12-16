# Quick Start Guide - Which Version to Use?

## 📦 Files Included

1. **quiz-screenshot-capture.html** - Original localStorage version
2. **quiz-screenshot-capture-indexeddb.html** - IndexedDB version (RECOMMENDED)
3. **README.md** - Full user guide
4. **INDEXEDDB_VERSION.md** - Technical details about IndexedDB version
5. **TESTING_CHECKLIST.md** - Comprehensive testing guide

## 🎯 Which Version Should You Use?

### Use IndexedDB Version (RECOMMENDED)
**File:** `quiz-screenshot-capture-indexeddb.html`

✅ **Use this if you:**
- Want to capture 10+ PNG screenshots per session
- Don't want to worry about storage limits
- Plan to store multiple quiz videos' screenshots
- Want better performance with large datasets
- Experienced the "QuotaExceededError" with the original version

**Benefits:**
- Store 50-100+ high-resolution screenshots
- No quota errors
- Better performance
- Future-proof

---

### Use localStorage Version (Original)
**File:** `quiz-screenshot-capture.html`

⚠️ **Only use this if you:**
- Need to work in very old browsers (pre-2013)
- Are storing very few screenshots (3-5 max)
- Prefer to export immediately after each capture
- Have specific compatibility requirements

**Limitations:**
- Maximum 3-5 PNG screenshots before quota error
- Must use JPEG format for more screenshots
- Need to export frequently

---

## 🚀 Recommended Workflow

### Step 1: Choose IndexedDB Version
Open `quiz-screenshot-capture-indexeddb.html` in your browser

### Step 2: Capture Your Screenshots
1. Load quiz video
2. Capture all 9 (or more) screenshots for that video
3. Fill in metadata for each
4. Save them all

### Step 3: Export When Done
- Click "📦 Export All (ZIP)"
- Saves everything in one organized package

### Step 4: Clear for Next Video
- Click "🗑️ Clear All"
- Start fresh with next video

### Step 5: Organize Your Exports
Keep your ZIP files organized by video:
```
Quiz Screenshots/
├── video-match-001.zip
├── video-match-002.zip
├── video-match-003.zip
└── ...
```

## 📊 Comparison Table

| Feature | localStorage | IndexedDB |
|---------|-------------|-----------|
| **Max PNG Screenshots** | 3-5 | 50-100+ |
| **Storage Limit** | ~5-10 MB | 50+ MB |
| **Performance** | Good | Better |
| **Quota Errors** | Yes | No |
| **Browser Support** | All | All modern |
| **Functionality** | Full | Full |
| **Recommended** | ❌ | ✅ |

## 🔄 Migrating from localStorage to IndexedDB

If you already used the localStorage version and have data:

### Option 1: Export First (Recommended)
1. Open `quiz-screenshot-capture.html` (old version)
2. Export your data as ZIP
3. Close that file
4. Start using `quiz-screenshot-capture-indexeddb.html`
5. Your exported data is safe in the ZIP file

### Option 2: Manual Import
1. Export from old version as JSON
2. Open new version
3. Open browser console (F12)
4. Use import code from INDEXEDDB_VERSION.md

**Note:** The two versions use different storage systems and don't share data automatically.

## 💡 Best Practices

### For Single Quiz Video:
1. Open IndexedDB version
2. Load and capture all screenshots
3. Export to ZIP
4. Clear database
5. Done!

### For Multiple Quiz Videos:
1. Open IndexedDB version once
2. Capture video 1 → Export → Clear
3. Capture video 2 → Export → Clear
4. Capture video 3 → Export → Clear
5. Keep app open between videos for efficiency

### For Large Sessions (20+ videos):
1. Capture and save all screenshots
2. Export ZIP every 5-10 videos
3. Clear database after each export
4. Prevents database from becoming too large

## 🐛 Troubleshooting

### "QuotaExceededError" in localStorage version
→ **Solution:** Switch to IndexedDB version immediately

### Data not saving
→ Check if you're using the right version
→ Verify browser isn't in private/incognito mode
→ Check browser console (F12) for errors

### Can't find my screenshots
→ Check which version you used
→ localStorage and IndexedDB store data separately
→ Export from the version you actually used

### App is slow with many screenshots
→ This is normal with 50+ screenshots
→ Export and clear database periodically
→ IndexedDB version handles this better than localStorage

## 📝 Quick Reference

### File Sizes
- localStorage version: ~46 KB
- IndexedDB version: ~48 KB
- Difference: ~2 KB (IndexedDB code)

### Open App
Simply double-click the HTML file or open it in your browser. No installation needed!

### Browser Console
Press **F12** to open developer tools and see:
- localStorage: "Loaded from localStorage"
- IndexedDB: "IndexedDB initialized successfully"

This tells you which version you're using.

## ✅ Final Recommendation

**Use `quiz-screenshot-capture-indexeddb.html` for everything.**

It solves the storage problem you encountered, works exactly the same way, and is future-proof. The localStorage version is only included for legacy/compatibility purposes.

---

## Questions?

Refer to:
- **README.md** - Complete user guide for all features
- **INDEXEDDB_VERSION.md** - Technical details about storage
- **TESTING_CHECKLIST.md** - Test all features

Both versions have identical functionality - the only difference is the storage mechanism under the hood. Choose IndexedDB and enjoy unlimited screenshot capacity! 🎉
