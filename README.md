# Fabrica Virtualis (FAVI)

Virtual Workspace for GSI

---

**FAVI** is the GSI's Virtual Workspace, where users can access the modules that we've created. Under the hood, this is where modules are integrated together into a complete functioning system.

> STATUS (VIII Augustii MMXXV)  
Planning stage

## DESIGN DOCUMENTS

- [FAVI System](static/design/favi-system.md)
- [FAVI Modules](static/design/favi-module.md)
- [FAVI Data Models](static/design/favi-data-models.md)

## ARCHITECTURE

**FAVI** will be composed of:

| Module | Full name | Transl. name | Role |
| --- | --- | --- | --- |
| TABA | Tabula Aetherea | Ethereal Tablet | System UI for the GSI Workspace | 
| EMEL | Editoris Melicorum | Editors of Melodies | GSI's music typesetting toolkit | 
| ETAB | Editoris Tabularum | Editors of Documents | GSI's document typesetting toolkit | 
| ARCA | Architectus Calculonis | Computerized Architect | GSI's 2D/3D modelling toolkit |

![FAVI system](./static/design/favi-system.svg "FAVI system")

## MODULE STRUCTURE

**FAVI** modules are packaged like so:

1. Modules use a **Docker container** which hosts a:
1. **Web server** that exposes functionality from:
1. the **Core module**

![FAVI module](./static/design/favi-module.svg "FAVI module")

This implementation allows users to tweak configurations as necessary. For customizing how these modules fit together, adding their own to the cluster, etc.

## DATA MODEL

**FAVI** is designed to handle the following file types:

![FAVI data models](./static/design/favi-data-models.svg "FAVI data models")
