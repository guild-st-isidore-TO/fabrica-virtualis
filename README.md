# Fabrica Virtualis (FAVI)

Virtual Workspace for GSI

---

**FAVI** is the GSI's Virtual Workspace, where users can access the modules that we've created. Under the hood, this is where modules are integrated together into a complete functioning system.

> STATUS (VIII Augustii MMXXV)  
Work in Progress -- Bootstrapping projects by reusing old code, getting containers running and ready for integration

## DESIGN DOCUMENTS

- [FAVI System](static/design/favi-system.md)
- [FAVI Modules](static/design/favi-module.md)
- [FAVI Data Models](static/design/favi-data-models.md)

## SYSTEM

**FAVI** will be a Docker cluster composed of the following main modules:

| Module | Full name | Transl. name | Role |
| --- | --- | --- | --- |
| [TABA](https://github.com/guild-st-isidore-TO/tabula-aetherea) | Tabula Aetherea | Ethereal Tablet | System UI for the GSI Workspace | 
| [EMEL](https://github.com/guild-st-isidore-TO/editorismelicorum) | Editoris Melicorum | Editors of Melodies | Music typesetting tools | 
| [ETAB](https://github.com/guild-st-isidore-TO/editoristabularum) | Editoris Tabularum | Editors of Documents | Document publishing tools | 
| [ARCA](https://github.com/guild-st-isidore-TO/architectuscalculonis) | Architectus Calculonis | Computerized Architect | 2D design / 3D modelling tools |

Modules planned for development:

| Planned module | Full name | Transl. name | Role |
| --- | --- | --- | --- |
| [CALI](https://github.com/guild-st-isidore-TO/calendarium-interretialum) | Calendarium Interretialum | Calendar of the Internet | Digital liturgical calendar |
| ???? | ???? | ???? | Image Processing Tools |
| ???? | ???? | ???? | Guitar Diagram Lib / Tools |

![FAVI system](./static/design/favi-system.svg "FAVI system")

### Typical Use Case

1. User accesses the system through their web browser.
1. User directs their browser to the TABA web page.
1. As the user interacts with the TABA UI, the TABA server interacts with the other FAVI modules via REST API.

For more information, please see [FAVI System](static/design/favi-system.md)

## MODULES

**FAVI** modules are packaged like so:

1. Modules use a **Docker container** which hosts the
1. **Module Web Server** that exposes functionality from
1. the **Module Core**

![FAVI module](./static/design/favi-module.svg "FAVI module")

This implementation allows users to tweak configurations as necessary. For customizing how these modules fit together, adding their own to the cluster, etc.

For more information, please see [FAVI Modules](static/design/favi-module.md)

## DATA MODELS

**FAVI** is designed to handle the following file types:

![FAVI data models](./static/design/favi-data-models.svg "FAVI data models")

For more information, please see [FAVI Data Models](static/design/favi-data-models.md)
