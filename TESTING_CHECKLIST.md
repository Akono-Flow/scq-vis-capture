# Quiz Screenshot Capture Tool - Testing Checklist

## Pre-Test Setup
- [ ] Open quiz-screenshot-capture.html in a modern browser
- [ ] Verify page loads without errors
- [ ] Check browser console (F12) for any error messages
- [ ] Prepare a test video file (any MP4, WebM, or OGG video)
- [ ] Have at least one test image ready

## Feature Testing

### 1. Video Player Functionality
- [ ] Click "Load Video" button
- [ ] Select a test video file
- [ ] Verify video loads and displays
- [ ] Test video controls (play, pause, seek, volume)
- [ ] Verify "Capture Frame" button becomes enabled
- [ ] Test progress bar (should show 0% initially)

### 2. Video Frame Capture
- [ ] Play video to a specific point
- [ ] Click "Capture Frame" button
- [ ] Verify frame appears in preview section
- [ ] Check timestamp is displayed correctly
- [ ] Verify Save button becomes enabled
- [ ] Test keyboard shortcut (Spacebar) for capture
  - Play video
  - Press Spacebar (ensure not focused on input)
  - Verify frame captured

### 3. Screen Capture
- [ ] Click "Screen Capture" button
- [ ] Browser prompts for screen selection
- [ ] Select entire screen or specific window
- [ ] Verify capture appears in preview
- [ ] Check Save button enabled
- [ ] Test canceling screen capture (should show error alert)

### 4. Clipboard Paste
- [ ] Copy an image to clipboard (from any source)
- [ ] Press Ctrl+V (Windows/Linux) or Cmd+V (Mac)
- [ ] Verify image appears in preview
- [ ] Check success alert displays
- [ ] Test with focus on different areas of page

### 5. File Upload
- [ ] Click "Upload File" button
- [ ] Select an image file from file picker
- [ ] Verify image appears in preview
- [ ] Check success alert displays
- [ ] Test with different image formats (PNG, JPEG, GIF)

### 6. Metadata Form - Name Field
- [ ] Type a name (e.g., "Giorgia Meloni")
- [ ] Verify field accepts input
- [ ] Check autocomplete (should be empty first time)
- [ ] Save screenshot
- [ ] Type same name again partially
- [ ] Verify autocomplete shows suggestion
- [ ] Click suggestion, verify it populates field
- [ ] Test with special characters (accents, apostrophes)

### 7. Metadata Form - Category Field
- [ ] Type a category (e.g., "World Leader")
- [ ] Verify field accepts input
- [ ] Save screenshot
- [ ] Test autocomplete with saved category
- [ ] Verify suggestions appear when typing
- [ ] Test clicking suggestion

### 8. Metadata Form - Subject Field
- [ ] Type a subject (e.g., "Local and International Affairs")
- [ ] Verify field accepts input
- [ ] Save screenshot
- [ ] Test autocomplete functionality
- [ ] Verify long text displays properly

### 9. Metadata Form - Description Field
- [ ] Type description text
- [ ] Test multi-line text entry
- [ ] Verify text area resizes
- [ ] Test with special characters
- [ ] Verify optional (form submits without it)

### 10. Knowledge Level Selector
- [ ] Verify default is "Unknown" (❓)
- [ ] Click "Don't Know" (❌)
- [ ] Verify it becomes active/highlighted
- [ ] Click "Know" (✅)
- [ ] Verify selection changes
- [ ] Click "Unknown" again
- [ ] Verify can switch back

### 11. Image Format Selector
- [ ] Verify default is PNG
- [ ] Select JPEG from dropdown
- [ ] Select WEBP
- [ ] Select GIF
- [ ] Verify selection persists until form submit

### 12. Save Screenshot
- [ ] Capture/load an image
- [ ] Fill all required fields (Name, Category, Subject)
- [ ] Click "Save Screenshot"
- [ ] Verify success alert appears
- [ ] Check screenshot appears in gallery
- [ ] Verify form resets after save
- [ ] Verify preview clears

### 13. Gallery Display
- [ ] Save multiple screenshots (at least 3)
- [ ] Verify all appear in gallery grid
- [ ] Check thumbnails display correctly
- [ ] Verify metadata shows (name, category, subject, size)
- [ ] Check timestamp shows for video captures
- [ ] Verify responsive grid layout

### 14. Gallery Stats
- [ ] Save screenshots with different subjects
- [ ] Check "Total Captures" updates
- [ ] Check "Subjects" count shows unique subjects
- [ ] Save screenshots with different categories
- [ ] Check "Categories" count shows unique categories
- [ ] Verify stats update in real-time

### 15. Gallery View Action
- [ ] Click "View" button on a screenshot
- [ ] Verify modal opens
- [ ] Check full-size image displays
- [ ] Verify all metadata displays correctly
- [ ] Click X to close modal
- [ ] Verify modal closes
- [ ] Click outside modal, verify closes

### 16. Gallery Delete Action
- [ ] Click "Delete" button on a screenshot
- [ ] Verify confirmation dialog appears
- [ ] Click Cancel, verify screenshot remains
- [ ] Click Delete again
- [ ] Confirm deletion
- [ ] Verify screenshot removed from gallery
- [ ] Check stats update accordingly

### 17. Progress Bar
- [ ] Start with 0 screenshots
- [ ] Save 3 screenshots
- [ ] Verify progress bar shows ~33%
- [ ] Save 6 more (9 total)
- [ ] Verify progress bar shows 100%
- [ ] Save 10th screenshot
- [ ] Verify bar stays at 100%

### 18. CSV Export
- [ ] Save at least 2 screenshots with full metadata
- [ ] Click "Export CSV"
- [ ] Verify file downloads (quiz-screenshots.csv)
- [ ] Open CSV in spreadsheet software
- [ ] Verify headers present
- [ ] Check all data rows present
- [ ] Verify no base64 image data in CSV
- [ ] Check special characters display correctly

### 19. Standard JSON Export
- [ ] Save screenshots with various metadata
- [ ] Click "Export Standard JSON"
- [ ] Verify file downloads (quiz-screenshots.json)
- [ ] Open in text editor
- [ ] Verify valid JSON format
- [ ] Check all fields present
- [ ] Verify base64 image data included
- [ ] Check imageData field starts with "data:image"

### 20. App JSON Export
- [ ] Save screenshots
- [ ] Click "Export App JSON"
- [ ] Verify file downloads (quiz-screenshots-app.json)
- [ ] Open in text editor
- [ ] Verify structure matches specification:
  - [ ] id field present
  - [ ] name field present
  - [ ] description field present
  - [ ] knowledge field present
  - [ ] src field with base64 data present
  - [ ] size field present
- [ ] Verify array format

### 21. ZIP Export
- [ ] Save multiple screenshots
- [ ] Click "Export All (ZIP)"
- [ ] Verify file downloads (quiz-screenshots-export.zip)
- [ ] Extract ZIP file
- [ ] Verify contains 4 items:
  - [ ] quiz-screenshots.csv
  - [ ] quiz-screenshots.json
  - [ ] quiz-screenshots-app.json
  - [ ] images folder
- [ ] Open images folder
- [ ] Verify all screenshots present as individual files
- [ ] Check filenames match IDs
- [ ] Verify file extensions match format selection

### 22. Clear All Functionality
- [ ] Save several screenshots
- [ ] Click "Clear All"
- [ ] Verify confirmation dialog appears
- [ ] Click Cancel, verify data remains
- [ ] Click "Clear All" again
- [ ] Confirm deletion
- [ ] Verify gallery empties
- [ ] Check stats reset to 0
- [ ] Verify empty state message displays
- [ ] Check export buttons become disabled

### 23. Session Persistence
- [ ] Save several screenshots
- [ ] Close the browser tab
- [ ] Reopen quiz-screenshot-capture.html
- [ ] Verify all screenshots still present
- [ ] Check autocomplete data persists
- [ ] Verify stats are correct
- [ ] Test closing and reopening multiple times

### 24. Alert Messages
- [ ] Test each capture method
- [ ] Verify success alerts display (green)
- [ ] Test capturing without image
- [ ] Verify error alert displays (red)
- [ ] Check alerts auto-dismiss after 3 seconds
- [ ] Verify informational alerts (blue) display

### 25. Autocomplete Behavior
- [ ] Type in name field
- [ ] Verify suggestions appear while typing
- [ ] Click outside field
- [ ] Verify suggestions disappear
- [ ] Type again
- [ ] Press down arrow key (if supported)
- [ ] Click suggestion
- [ ] Verify field populates

### 26. Form Validation
- [ ] Capture image
- [ ] Try to save without Name
- [ ] Verify validation prevents submit
- [ ] Add Name, try without Category
- [ ] Verify validation prevents submit
- [ ] Add Category, try without Subject
- [ ] Verify validation prevents submit
- [ ] Complete all required fields
- [ ] Verify form submits successfully

### 27. Responsive Design
- [ ] Resize browser window to small width
- [ ] Verify layout adapts (single column)
- [ ] Test on mobile device if available
- [ ] Check all buttons accessible
- [ ] Verify gallery grid responds to width
- [ ] Test video player responsiveness

### 28. Image Format Conversion
- [ ] Capture a screenshot
- [ ] Select JPEG format
- [ ] Save screenshot
- [ ] Export ZIP
- [ ] Check image file has .jpeg extension
- [ ] Repeat with PNG, WEBP, GIF
- [ ] Verify each saves with correct extension

### 29. Error Handling
- [ ] Try screen capture without granting permission
- [ ] Verify error alert displays
- [ ] Try pasting non-image data
- [ ] Verify no error or appropriate message
- [ ] Try saving with empty form
- [ ] Verify validation works

### 30. Performance Testing
- [ ] Save 20+ screenshots
- [ ] Verify app remains responsive
- [ ] Test scrolling gallery
- [ ] Test export functions with large dataset
- [ ] Check browser memory usage
- [ ] Verify localStorage capacity handling

## Edge Cases

### Special Characters
- [ ] Test name with accents (é, ñ, ü)
- [ ] Test name with apostrophes (O'Brien)
- [ ] Test description with quotes
- [ ] Test description with line breaks
- [ ] Verify CSV export handles special chars

### Large Files
- [ ] Capture high-resolution screenshot
- [ ] Verify size displays correctly
- [ ] Test saving multiple large images
- [ ] Check export performance

### Browser Compatibility
- [ ] Test in Chrome
- [ ] Test in Firefox
- [ ] Test in Edge
- [ ] Test in Safari (if available)
- [ ] Note any browser-specific issues

## Security Testing
- [ ] Verify no data sent to external servers
- [ ] Check Network tab (F12) for external requests
- [ ] Confirm localStorage only storage method
- [ ] Test in private/incognito mode (data shouldn't persist)

## Issues Found
Document any bugs or issues discovered during testing:

1. 
2. 
3. 

## Test Results Summary
- Total Tests: 100+
- Passed: 
- Failed: 
- Not Tested: 
- Issues Found: 

## Notes
Add any additional observations or recommendations:

---

**Tester Name**: ________________  
**Date**: ________________  
**Browser**: ________________  
**Browser Version**: ________________  
**Operating System**: ________________  
**Test Duration**: ________________
