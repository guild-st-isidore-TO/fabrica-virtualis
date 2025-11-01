# Milestones / Roadmap

Back to [main README](../../README.md)

---

The next iteration of GSI’s workspace

The **FaVirtu** (renamed from FAVI) design retains the idea of a Docker container cluster. But the addition of a component library (**LibRext**) opened up some possibilities for a better and more realistic implementation path.

## Features

### v2.2

- Web-based UI for accessing GSI tools
- Document creation via MD/MDX on the browser

### v2.3

- Music score creation via GABC/LY files on system

### v2.5

- Parallel scripture passages

### v2.6

- Image processing

## Design

Sequence/Data Flow Diagram 1.0

![image.png](attachment:793c14d2-d029-4775-872a-019941f4ed37:image.png)

## Roadmap & Implementation Path

### 2.0

- Lay out foundations for **LibRext**
- Build it up to the point where it can export:
    - stylesheets
    - React components for the **TabAeth UI**
    - React components for a Markdown parser

### 2.1

- Lay out foundations for **EdTab**
- Build it up to the point where it can consume LibRext stylesheets and components, and create docs from Markdown/MDX

### 2.2

- Rename, refactor and upgrade **TabAeth**
- Build it up to the point where it can:
    - consume LibRext stylesheets and components
    - consume EdTab endpoints and be invoked on the UI
- Implement code editor on UI that sends raw MD/MDX to EdTab, and displays the returned document or a package of documents.

### 2.3

- Rename, refactor and upgrade **EdiMeli**
- Build it up to the point where it can receive JSON parameters and return a document, or a package of documents.
- Implement control panel UI on **TabAeth** and, that allows user to configure **EdiMeli** options and generate scores. The system would then send a config JSON, and return a document or a package of documents.

### 2.4

- Refactor and upgrade **MAtte**
- Implement control panel UI on **TabAeth** for using the **MAtte** service

### 2.5

- Lay out foundations and reuse old code for **ArPictu**
- Build it up to the point where it can receive Image files and JSON parameters and return modified images
- Implement control panel UI on **TabAeth** for using the **ArPictu** service