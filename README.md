# 5E Static LMS Tool

A three-part, zero-backend web application suite for robotics classrooms that operates entirely via your school's existing LMS.

## Components

### 1. Lesson Builder (`builder.html`)
**Teacher Side - Local Setup**

- Open `builder.html` in any modern web browser
- Fill in lesson parameters:
  - Lesson Title
  - Engage scenario text and image (optional)
  - Unlock Code (PIN) for the Explain section
  - Explain solution text
- Click "Generate Lesson Package" to download `index.html`
- Upload `index.html` to your LMS using the HTML5 resource tool

### 2. Student App (`index.html` - Generated)
**LMS Side - Deployed**

Students interact with a 5E model lesson:
1. **Engage** - View scenario and image
2. **Explore** - Text input for predictions
3. **Explain** - Enter PIN to unlock solution
4. **Elaborate** - Paste screenshots (Ctrl+V) or drag & drop images
5. **Evaluate** - Reflection text input

Clicking "Finish & Save" downloads a JSON file with all responses, which students upload back to the LMS.

### 3. Auto-Grader Dashboard (`grader.html`)
**Teacher Side - Local Review**

- Open `grader.html` in any modern web browser
- Drag & drop multiple student JSON files simultaneously
- View a clean dashboard with:
  - Student names
  - Text responses for Explore and Evaluate sections
  - Rendered screenshots from Elaborate section
  - Statistics (total submissions, images count, etc.)
- Click images to view full-size
- No server or database required

## Technical Details

- **Zero Backend**: All processing happens client-side in the browser
- **Vanilla Stack**: Pure HTML5, CSS3, and JavaScript (no frameworks)
- **Local-First**: No cloud dependencies or external services
- **Image Compression**: Screenshots are compressed to WebP format using HTML5 Canvas
- **Data Export**: Student data packaged as JSON files via browser download API

## Browser Compatibility

Works in all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari

## File Structure

```
5e-lms-tool/
├── builder.html          # Teacher lesson creation tool
├── grader.html           # Teacher grading dashboard
├── sample_submission.json # Example student submission
└── README.md             # This file
```

## Usage Workflow

1. **Teacher creates lesson**: Open `builder.html` → fill form → download `index.html`
2. **Teacher uploads to LMS**: Upload `index.html` as HTML5 resource
3. **Student completes lesson**: Open lesson in LMS → complete 5E activities → download JSON
4. **Student submits work**: Upload JSON file to LMS assignment portal
5. **Teacher reviews**: Download all JSONs → open `grader.html` → drag & drop files → review

## License

Free to use for educational purposes.
