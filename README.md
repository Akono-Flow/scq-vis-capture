# Quiz Screenshot Capture Tool - User Guide

## Overview
A comprehensive web application for capturing, annotating, and exporting screenshots from quiz videos with rich metadata management and multiple export formats.

## Features

### 🎬 Video Integration
- Load quiz videos directly in the app
- Full video player controls (play, pause, seek, volume)
- Capture frames at any point with spacebar shortcut
- Automatic timestamp recording

### 📸 Multiple Capture Methods
1. **Video Frame Capture**: Capture current frame from loaded video
2. **Screen Capture**: Capture entire screen or specific window (uses browser's screen sharing API)
3. **Clipboard Paste**: Press Ctrl/Cmd + V to paste images from clipboard
4. **File Upload**: Browse and select images from your computer

### ✏️ Rich Metadata Management
- **Name**: Person/item identification (with autocomplete)
- **Category**: Classification type (with autocomplete)
- **Subject**: Topic area (Local & International Affairs, Theatre & Cinema, Sports, etc.) (with autocomplete)
- **Description**: Free-text additional information
- **Knowledge Level**: Tristate selector
  - ❓ Unknown (-1) - Default
  - ❌ Don't Know (0)
  - ✅ Know (1)
- **Image Format**: Convert to PNG, JPEG, WEBP, or GIF
- **Video Timestamp**: Automatically captured from video

### 💾 Session Persistence
- All captured screenshots automatically saved to browser's localStorage
- Data persists across browser sessions
- Can safely close and reopen the app without losing work
- Autocomplete suggestions learn from your inputs

### 📊 Gallery View
- Grid display of all captured screenshots
- Preview thumbnails with metadata
- Quick view and delete actions
- Real-time statistics:
  - Total captures count
  - Unique subjects count
  - Unique categories count
- Progress bar shows completion (based on 9 screenshots target)

### 📤 Export Options

#### 1. CSV Export (`quiz-screenshots.csv`)
Contains all metadata fields (no base64 images):
- ID, Name, Category, Subject, Description
- Knowledge, Format, Timestamp, Size, Captured At

#### 2. Standard JSON Export (`quiz-screenshots.json`)
Complete data export including:
- All metadata fields
- Base64-encoded images
- Full screenshot information for archival

#### 3. App JSON Export (`quiz-screenshots-app.json`)
Custom format for your other application:
```json
[
  {
    "id": "img-1734234567890-abc123",
    "name": "Giorgia Meloni",
    "description": "Prime Minister of Italy",
    "knowledge": -1,
    "src": "data:image/png;base64,iVBORw...",
    "size": "4.2 KB"
  }
]
```

#### 4. ZIP Export (`quiz-screenshots-export.zip`)
Complete package containing:
- `quiz-screenshots.csv` - CSV data file
- `quiz-screenshots.json` - Standard JSON with base64
- `quiz-screenshots-app.json` - App-specific JSON
- `images/` folder - All screenshots as individual image files

## Usage Instructions

### Getting Started
1. Open `quiz-screenshot-capture.html` in a modern web browser (Chrome, Edge, Firefox, Safari)
2. No installation or server required - runs entirely in the browser

### Capturing from Video
1. Click "📁 Load Video" button
2. Select your quiz match video file
3. Play the video using the controls
4. When you see a visual to capture:
   - Press **Spacebar** or click "📸 Capture Frame"
   - The frame is captured and displayed in the preview
5. Fill in the metadata form
6. Click "💾 Save Screenshot"

### Capturing from Other Sources

**Screen Capture:**
1. Click the "🖥️ Screen Capture" button
2. Browser will prompt you to select screen/window
3. Select what you want to capture
4. Image appears in preview
5. Fill in metadata and save

**Clipboard Paste:**
1. Copy an image to clipboard (from anywhere)
2. Press **Ctrl+V** (Windows/Linux) or **Cmd+V** (Mac)
3. Image appears in preview
4. Fill in metadata and save

**File Upload:**
1. Click "📂 Upload File" button
2. Browse and select an image file
3. Image appears in preview
4. Fill in metadata and save

### Metadata Form Tips

**Autocomplete:**
- As you type in Name, Category, or Subject fields, suggestions appear
- Suggestions are based on previously entered values
- Click a suggestion or keep typing to add new values

**Knowledge Level:**
- Click the appropriate icon to select knowledge level
- Default is ❓ Unknown (-1)
- Changes to ❌ Don't Know (0) or ✅ Know (1) as needed

**Image Format:**
- **PNG**: Best quality, larger file size (default)
- **JPEG**: Smaller size, good for photos
- **WEBP**: Modern format, excellent compression
- **GIF**: Supports animation (if source is animated)

### Managing Captured Screenshots

**View Details:**
- Click "👁️ View" button on any gallery item
- See full-size image and all metadata
- Close with X or click outside modal

**Delete Screenshot:**
- Click "🗑️" button on gallery item
- Confirm deletion
- Screenshot removed from session

**Clear All:**
- Click "🗑️ Clear All" button in export section
- Confirms before deleting everything
- Removes all data from localStorage

### Exporting Data

**Single Export:**
- Click appropriate export button (CSV, Standard JSON, App JSON)
- File downloads immediately
- Data exported in selected format only

**ZIP Export (Recommended):**
- Click "📦 Export All (ZIP)"
- Downloads single ZIP file containing:
  - All three data formats (CSV + both JSONs)
  - Individual image files in `images/` folder
- Complete backup of entire session

## Keyboard Shortcuts

- **Spacebar**: Capture frame from video (when video is active and page is not focused on input fields)
- **Ctrl/Cmd + V**: Paste image from clipboard

## Technical Details

### Browser Requirements
- Modern browser with HTML5 support
- JavaScript enabled
- LocalStorage enabled
- For screen capture: Browser with getDisplayMedia API support

### Data Storage
- All data stored in browser's localStorage
- Key: `quizScreenshots`
- Persists until manually cleared or browser data deleted
- No server communication - completely offline

### Image Processing
- Screenshots captured as base64 data URLs
- Format conversion done client-side using Canvas API
- File sizes calculated from base64 string length
- Quality: PNG uses lossless compression

### ID Generation
- Format: `img-[timestamp]-[random]`
- Example: `img-1734234567890-abc123`
- Timestamp: Current Unix timestamp in milliseconds
- Random: 7-character alphanumeric string
- Ensures uniqueness across sessions

## Workflow Example

**Typical 9-Screenshot Session:**

1. Load quiz video
2. Start playing video
3. When visual appears:
   - Press Spacebar to capture
   - Enter name (e.g., "Giorgia Meloni")
   - Enter category (e.g., "World Leader")
   - Enter subject (e.g., "Local and International Affairs")
   - Optionally add description
   - Select knowledge level
   - Choose image format if not PNG
   - Click Save
4. Continue for all 9 visuals (or however many needed)
5. Review gallery to verify all captures
6. Click "📦 Export All (ZIP)" for complete backup
7. Optionally export specific formats as needed

## Tips & Best Practices

1. **Save frequently**: Each screenshot is automatically saved to localStorage upon clicking "Save Screenshot"
2. **Use autocomplete**: Take advantage of suggestions to maintain consistency
3. **Name consistently**: Use full names (e.g., "Barack Obama" not "Obama")
4. **Categorize clearly**: Be specific (e.g., "Prime Minister" vs "Politician")
5. **Subject organization**: Use the three main categories consistently:
   - Local and International Affairs
   - Theatre and Cinema
   - Sports
6. **Export often**: Export to ZIP after completing each video session
7. **Clear after export**: After successful export and backup, clear the session for next video

## Troubleshooting

**Video won't load:**
- Check file format (MP4, WebM, OGG supported)
- Try a different browser
- Ensure file isn't corrupted

**Screen capture not working:**
- Grant browser permissions when prompted
- Try a different browser (works best in Chrome/Edge)
- Check browser security settings

**Clipboard paste not working:**
- Ensure you've copied an image (not text)
- Try using the upload method instead
- Check browser clipboard permissions

**Exports not downloading:**
- Check browser download settings
- Ensure pop-ups aren't blocked
- Check available disk space

**Data lost after closing browser:**
- Check if localStorage is enabled
- Verify you're using the same browser
- Check if browser is in private/incognito mode (data won't persist)

## Browser Compatibility

**Fully Supported:**
- Google Chrome 90+
- Microsoft Edge 90+
- Firefox 88+
- Safari 14+

**Partially Supported:**
- Older browsers may not support screen capture API
- Mobile browsers may have limited functionality

## Security & Privacy

- No data sent to any server
- All processing done locally in browser
- No tracking or analytics
- No external dependencies except JSZip (loaded from CDN)
- Safe to use with sensitive quiz content

## File Information

- **File Name**: quiz-screenshot-capture.html
- **File Type**: Single HTML file (no dependencies except JSZip CDN)
- **Size**: ~1,300 lines
- **Technologies**: HTML5, CSS3, Vanilla JavaScript
- **External Library**: JSZip (for ZIP export functionality)

## Updates & Modifications

To customize the app:
1. Open the HTML file in a text editor
2. Modify CSS in `<style>` section for appearance changes
3. Modify JavaScript in `<script>` section for functionality changes
4. Default target is 9 screenshots (change in progress calculation if needed)

## Support

For issues or questions:
1. Check this README thoroughly
2. Verify browser compatibility
3. Test in different browser
4. Check browser console for error messages (F12 > Console)

---

**Version**: 1.0
**Author**: M. Cole
**Last Updated**: December 2024  
**Created for**: Quiz Screenshot Workflow Automation
