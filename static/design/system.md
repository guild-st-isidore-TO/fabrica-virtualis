# FAVI System

Back to [main README](../../README.md)

---

**FAVI** will be a Docker cluster composed of the following elements:

![FAVI system](./img/favi-system-1.1.svg "FAVI system")

### System Modules

| Module | Slug | Full name | Role |
| --- | --- | --- | --- |
| **TabAeth** | `tabaeth` | Tabula Aetherea / Ethereal Tablet | System UI for the GSI Workspace | 

### API Modules

| Module | Slug | Full name | Role |
| --- | --- | --- | --- |
| **EdiMeli** | `edimeli` | Editoris Melicorum / Editors of Melodies | Music typesetting tools | 
| **EdTab** | `edtab` | Editoris Tabularum / Editors of Documents | Document publishing tools | 
| **ArchAlc** | `archalc` | Architectus Calculonis / Computerized Architect | 2D design / 3D modelling tools |
| **MAtte** | `matte` | Manípulus Attestatiónum / Sheaf of Testimonies | Building multilingual parallel scripture passages |

### Libraries

| Library | Slug | Full name | Role |
| --- | --- | --- | --- |
| **LibRext** | `librext` | Librarium Textuum / Library of Frameworks | UI design system and component library |
| **ArCodi** | `arcodi` | Armamentarium Codicum / Armory of Books | Code and function library. |

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

