# FAVI Modules

Back to [main README](../../README.md)

---

**FAVI** modules are packaged like so:

1. Modules use a **Docker container** which hosts the
1. **Module Web Server** that exposes functionality from
1. the **Module Core**

![FAVI module](./favi-module.svg "FAVI module")

This implementation allows users to tweak configurations as necessary. For customizing how these modules fit together, adding their own to the cluster, etc.

#### Tech Stacks

The base Docker image and web server platform should match the core module's tech stack.

| Module | Core Techs | Notes |
| --- | --- | --- |
| TABA | JavaScript, Node, Next, Electron | ... |
| EMEL | Python, LilyPond | ... |
| ETAB | Python, Pandoc | ... |
| ARCA | Python, FreeCAD | ... |
