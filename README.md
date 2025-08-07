# Fabrica Virtualis (FAVI)

Virtual Workspace for GSI

---

**FAVI** is the GSI's Virtual Workspace, where users can access the modules that we've created. Under the hood, this is where modules are integrated together into a complete functioning system.

> STATUS (VII Augustii MMXXV)  
Planning stage

## ARCHITECTURE

**FAVI** will be composed of:

| Module | Full name | Transl. name | Role |
| --- | --- | --- | --- |
| TABA | Tabula Aetherea | Ethereal Tablet | System UI for the GSI Workspace | 
| EMEL | Editoris Melicorum | Editors of Melodies | GSI's music typesetting toolkit | 
| ETAB | Editoris Tabularum | Editors of Documents | GSI's document typesetting toolkit | 
| ARCA | Architectus Calculonis | Computerized Architect | GSI's 2D/3D modelling toolkit |

![FAVI system](./static/design/favi-system.svg "FAVI system")

### MODULES

**FAVI** modules are packaged like so:

1. Modules use a **Docker container** which hosts a:
1. **Web server** that exposes functionality from:
1. the **Core module**

![FAVI module](./static/design/favi-module.svg "FAVI module")

#### Tech Stacks

The base Docker image and web server platform should match the core module's tech stack.

| Module | Core Techs | Notes |
| --- | --- | --- |
| TABA | JavaScript, Node, Next, Electron | ... |
| EMEL | Python, LilyPond | ... |
| ETAB | Python, Pandoc | ... |
| ARCA | Python, FreeCAD | ... |
