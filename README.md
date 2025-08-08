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

## SYSTEM

**FAVI** will be a Docker cluster composed of the following main modules:

| Module | Full name | Transl. name | Role |
| --- | --- | --- | --- |
| [TABA](https://github.com/guild-st-isidore-TO/tabula-aetherea) | Tabula Aetherea | Ethereal Tablet | System UI for the GSI Workspace | 
| [EMEL](https://github.com/guild-st-isidore-TO/editorismelicorum) | Editoris Melicorum | Editors of Melodies | GSI's music typesetting toolkit | 
| [ETAB](https://github.com/guild-st-isidore-TO/editoristabularum) | Editoris Tabularum | Editors of Documents | GSI's document typesetting toolkit | 
| [ARCA](https://github.com/guild-st-isidore-TO/architectuscalculonis) | Architectus Calculonis | Computerized Architect | GSI's 2D/3D modelling toolkit |

![FAVI system](./static/design/favi-system.svg "FAVI system")

### Typical Use Case

1. User accesses the system through their web browser.
1. User directs their browser to the TABA web page.
1. As the user interacts with the TABA UI, the TABA server interacts with the other FAVI modules via REST API.

## MODULES

**FAVI** modules are packaged like so:

1. Modules use a **Docker container** which hosts the
1. **Module Web Server** that exposes functionality from
1. the **Module Core**

![FAVI module](./static/design/favi-module.svg "FAVI module")

This implementation allows users to tweak configurations as necessary. For customizing how these modules fit together, adding their own to the cluster, etc.

## DATA MODELS

**FAVI** is designed to handle the following file types:

![FAVI data models](./static/design/favi-data-models.svg "FAVI data models")
