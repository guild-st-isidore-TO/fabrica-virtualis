# FaVirtu Module

Back to [main README](../../README.md)

---

## API Modules

**FaVirtu API** modules are packaged like so:

1. API Modules use a **Docker container** which hosts the
1. **Module Web Server** that exposes functionality from
1. the **Module Core**

![FaVirtu module](./img/favi-module-1.0.svg "FaVirtu module")

This implementation allows users to tweak configurations as necessary. For customizing how these modules fit together, adding their own to the cluster, etc.

#### Tech Stacks

The base Docker image and web server platform should match the core module's tech stack.

| Module | Core Techs | Notes |
| --- | --- | --- |
| TabAeth | JavaScript, Node, Next, Electron | ... |
| EdiMeli | Python, LilyPond | ... |
| EdTab | Python, Pandoc | ... |
| ArchAlc | Python, FreeCAD | ... |
