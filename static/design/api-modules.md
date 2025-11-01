# API Modules

Back to [main README](../../README.md)

---

| Module | Slug | Full name | Role |
| --- | --- | --- | --- |
| **EdiMeli** | `edimeli` | Editoris Melicorum / Editors of Melodies | Music typesetting tools | 
| **EdTab** | `edtab` | Editoris Tabularum / Editors of Documents | Document publishing tools | 
| **ArchAlc** | `archalc` | Architectus Calculonis / Computerized Architect | 2D design / 3D modelling tools |
| **ArPictu** | `arpictu` | Artifex Picturarum | Image processing tools |
| **MAtte** | `matte` | Manípulus Attestatiónum / Sheaf of Testimonies | Building multilingual parallel scripture passages |

## COMMON

Functions common to all FaVirtu modules

### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| Heartbeat/Handshake | `ping` | ... |
| Info Report | `info` | ... |
| Status Report | `status` | ... |

## EdiMeli

https://github.com/guild-st-isidore-TO/editorismelicorum  
Core techs: Python, LilyPond, gabctk

Editoris Melicorum is a digital music typesetting toolkit for music ministries in Catholic parishes. The toolkit helps build musical arrangements around traditional hymns in Gregorian notation. As well as laying them out into documents, both for the congregation and the choir/musicians.

### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| Arrangement sheets | `arr_sheets` | ... |
| Performance sheets | `perf_sheets` | ... |

### arr_sheets

returns **PDF documents**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `source_gabc_files` | GabcFile[] | ... |
| `source_ly_files` | LilyPondFile[] | ... |
| `config` | object | Configurations and settings |

### perf_sheets

returns **PDF documents**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `source_gabc_files` | GabcFile[] | ... |
| `source_ly_files` | LilyPondFile[] | ... |
| `input_ly_files` | LilyPondFile[] | ... |
| `config` | object | Configurations and settings |

## EdTab

https://github.com/guild-st-isidore-TO/editoristabularum  
Core techs: Python, Pandoc, LaTEX

The Editoris Tabularum is a digital typesetting toolkit for creating (low-key) multimedia and multilingual documents like prayer booklets, mass and liturgical programs, parish announcements, etc. Think of something that can create liturgy programs combining text (in English/Latin/French), images (covers, ornaments), and music scores (hymns, chants).

### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| Quote | `quote` | Basic multilingual document. Can be used for scripture quotes, prayers, booklets, etc. |
| Program | `program` | Multilingual mass / liturgical programs. |
| Hymnal | `hymnal` | Multilingual hymnals and chanted liturgies |

### quote

returns **PDF document**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `config` | object | Configurations and settings |

### program

returns **PDF document**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `config` | object | Configurations and settings |

### hymnal

returns **PDF document**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `config` | object | Configurations and settings |

## ArchAlc

https://github.com/guild-st-isidore-TO/architectuscalculonis  
Core techs: Python, FreeCAD

The Architectus Calculonis is a parametric 2D/3D modelling toolkit that creates 2D designs (SVG) for documents and 3D models (STL, 3MF) for useful things in parish activities

### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| 2D Frame | `frame_2d` | Creates an SVG frame with the given size and parameters |

### frame_2d

returns **SVG image**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `ext_length` | number | ... |
| `ext_width` | number | ... |
| `ext_corner_style` | string | ... |
| `int_length` | number | ... |
| `int_width` | number | ... |
| `int_corner_style` | string | ... |
| `config` | object | Configurations and settings |
