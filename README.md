# Fabrica Virtualis (FAVI)

Virtual Workspace for GSI

---

**FAVI** is the GSI's Virtual Workspace, where users can access the modules that we've created. Under the hood, this is where modules are integrated together into a complete functioning system.

> STATUS (XXVIII Octobris MMXXV)  
On Hold -- Under active redesign

## DESIGN

- [FAVI System](static/design/favi-system.md)
- [FAVI Modules](static/design/favi-module.md)
- [FAVI Data Models](static/design/favi-data-models.md)

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

For more information, please see [FAVI Modules](static/design/favi-module.md)

## DATA MODELS

**FAVI** is designed to handle the following file types:

![FAVI data models](./static/design/favi-data-models.svg "FAVI data models")

For more information, please see [FAVI Data Models](static/design/favi-data-models.md)
