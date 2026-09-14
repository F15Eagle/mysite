# Supported Syntax Reference

This system processes standard Markdown along with custom inline shortcodes for interactive components.

---

## 1. Standard Markdown

### Headings
# Heading 1
## Heading 2
### Heading 3

### Text Formatting
**Bold text**
*Italic text*
`Inline code`

### Lists
Unordered:
* Bullet point item
* Another item

Ordered:
1. First item
2. Second item

### Links & Images (Native Markdown)
[Link Text](https://example.com)
![Image Alt Text](/assets/images/sample.jpg)

### Blockquotes
> Highlighting a note or engineering design quote.

### Image with Caption
[[image: /assets/images/architecture.png, Architecture Diagram]]

### Local Video Embed
[[video: /assets/videos/demo.mp4, System Overview Walkthrough]]

### Media Carousel (images and videos)
[[carousel: /assets/img1.jpg; /assets/demo.mp4; /assets/img2.jpg]]

### YouTube Video Embed
[[youtube: [https://www.youtube.com/watch?v=dQw4w9WgXcQ](https://www.youtube.com/watch?v=dQw4w9WgXcQ), Demo Video]]
[[youtube: dQw4w9WgXcQ, Demo Video]]

### PDF Viewer Badge
[[pdf: /assets/docs/report.pdf, Technical Report]]

### Inline PDF Viewer
[[pdf: /assets/docs/report.pdf, Technical Report, true]]

### Styled Link
[[link: [https://github.com/project](https://github.com/project), Source Code Repository]]

### Code Blocks
```javascript
console.log("Hello, World!");
