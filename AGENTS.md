# AGENTS.md

## Cursor Cloud specific instructions

This repository contains a single self-contained HTML file (`全国机器人实验室人才情报平台.html`) — a static Chinese Robotics Lab Talent Intelligence Platform. There is no build system, package manager, or backend.

### Running the application

Serve the file with any static HTTP server from the workspace root:

```
python3 -m http.server 8080
```

Then open in Chrome: `http://localhost:8080/%E5%85%A8%E5%9B%BD%E6%9C%BA%E5%99%A8%E4%BA%BA%E5%AE%9E%E9%AA%8C%E5%AE%A4%E4%BA%BA%E6%89%8D%E6%83%85%E6%8A%A5%E5%B9%B3%E5%8F%B0.html`

### Notes

- No dependencies to install, no lint/test/build tooling exists.
- The HTML file loads Google Fonts via CDN; without internet the page still works with fallback system fonts.
- The filename contains Chinese characters — always URL-encode it when referencing via HTTP.
