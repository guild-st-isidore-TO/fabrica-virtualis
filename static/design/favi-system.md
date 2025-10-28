# FAVI System

Back to [main README](../../README.md)

---

> STATUS (XI Augustii MMXXV)  
Work in Progress -- Designing API endpoints, inputs, etc

**FAVI** will be a Docker cluster composed of the following main modules:

| Module | Module Slug | Full name | Role |
| --- | --- | --- | --- |
| **TabAeth** | `tabaeth` | Tabula Aetherea / Ethereal Tablet | System UI for the GSI Workspace | 
| **EdiMeli** | `edimeli` | Editoris Melicorum / Editors of Melodies | Music typesetting tools | 
| **EdTab** | `edtab` | Editoris Tabularum / Editors of Documents | Document publishing tools | 
| **ArchAlc** | `archalc` | Architectus Calculonis / Computerized Architect | 2D design / 3D modelling tools |
| **MAtte** | `matte` | Manípulus Attestatiónum / Sheaf of Testimonies | Building multilingual parallel scripture passages |
| **LibRext** | `librext` | Librarium Textuum / Library of Frameworks | UI design system and component library |

## USE CASE, DATA FLOW

### Typical Use Case

1. User accesses the system through their web browser.
1. User directs their browser to the TABA web page.
1. As the user interacts with the TABA UI, the TABA server interacts with the other FAVI modules via REST API.

### Data flow

User interactions are expected to have this data flow:

1. On TABA front-end, user selects an available FAVI function
1. On the corresponding TABA page for that FAVI function, user makes changes to app behaviour (configs)
1. On the same page, user selects the relevant files and data (inputs)
1. On the same page, user triggers FAVI function
1. TABA back-end sends user's configs and input data to FAVI module's web server
    - config/inputs to be sent as JSON in HTTP request
1. FAVI module serveruns module's core function using user's configs and inputs
1. FAVI module core returns valid data, or throws an exception
    - valid data (e.g.utput images and PDFs) to be returnedHTTP response
1. FAVI module server returns valid data or exception data
1. TABA back-end parses data from FAVI module
1. TABA front-end shows valid result, or error message

## MAIN MODULES

### COMMON

Functions common to all FAVI modules

#### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| Heartbeat/Handshake | `ping` | ... |
| Info Report | `info` | ... |
| Status Report | `status` | ... |

### TabAeth

https://github.com/guild-st-isidore-TO/tabula-aetherea  
Core techs: JavaScript, Node, React, [Refine](https://refine.dev/)

Tabula Aetherea is GSI's System UI, the main webpage and user interface for the apps we've created. Accessible through a web browser, and allows data entry and file uploading into the system. As users access the TABA front-end, the TABA server will use the appropriate FAVI module to complete tasks.

### EdiMeli

https://github.com/guild-st-isidore-TO/editorismelicorum  
Core techs: Python, LilyPond, gabctk

Editoris Melicorum is a digital music typesetting toolkit for music ministries in Catholic parishes. The toolkit helps build musical arrangements around traditional hymns in Gregorian notation. As well as laying them out into documents, both for the congregation and the choir/musicians.

#### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| Arrangement sheets | `arr_sheets` | ... |
| Performance sheets | `perf_sheets` | ... |

#### arr_sheets

returns **PDF documents**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `source_gabc_files` | GabcFile[] | ... |
| `source_ly_files` | LilyPondFile[] | ... |
| `config` | object | Configurations and settings |

#### perf_sheets

returns **PDF documents**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `source_gabc_files` | GabcFile[] | ... |
| `source_ly_files` | LilyPondFile[] | ... |
| `input_ly_files` | LilyPondFile[] | ... |
| `config` | object | Configurations and settings |

### EdTab

https://github.com/guild-st-isidore-TO/editoristabularum  
Core techs: Python, Pandoc, LaTEX

The Editoris Tabularum is a digital typesetting toolkit for creating (low-key) multimedia and multilingual documents like prayer booklets, mass and liturgical programs, parish announcements, etc. Think of something that can create liturgy programs combining text (in English/Latin/French), images (covers, ornaments), and music scores (hymns, chants).

#### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| Quote | `quote` | Basic multilingual document. Can be used for scripture quotes, prayers, booklets, etc. |
| Program | `program` | Multilingual mass / liturgical programs. |
| Hymnal | `hymnal` | Multilingual hymnals and chanted liturgies |

#### quote

returns **PDF document**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `config` | object | Configurations and settings |

#### program

returns **PDF document**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `config` | object | Configurations and settings |

#### hymnal

returns **PDF document**

| Input property name | Data type | Notes |
| --- | --- | --- |
| `document` | DocumentFile | ... |
| `config` | object | Configurations and settings |

### ArchAlc

https://github.com/guild-st-isidore-TO/architectuscalculonis  
Core techs: Python, FreeCAD

The Architectus Calculonis is a parametric 2D/3D modelling toolkit that creates 2D designs (SVG) for documents and 3D models (STL, 3MF) for useful things in parish activities

#### API Endpoints

| Function | API Endpoint | Notes |
| --- | --- | --- |
| 2D Frame | `frame_2d` | Creates an SVG frame with the given size and parameters |

#### frame_2d

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
