# FAVI System

Back to [main README](../../README.md)

## ARCHITECTURE

**FAVI** will be composed of:

| Module | Full name | Transl. name | Role |
| --- | --- | --- | --- |
| TABA | Tabula Aetherea | Ethereal Tablet | System UI for the GSI Workspace | 
| EMEL | Editoris Melicorum | Editors of Melodies | GSI's music typesetting toolkit | 
| ETAB | Editoris Tabularum | Editors of Documents | GSI's document typesetting toolkit | 
| ARCA | Architectus Calculonis | Computerized Architect | GSI's 2D/3D modelling toolkit |

![FAVI system](./favi-system.svg "FAVI system")

### Main Modules

#### TABA

https://github.com/guild-st-isidore-TO/tabula-aetherea

Tabula Aetherea is GSI's System UI, the main interface for the apps we've created. When users access the TABA front-end, the TABA server will use the appropriate FAVI module to complete tasks.

#### EMEL

https://github.com/guild-st-isidore-TO/editorismelicorum

Editoris Melicorum is a digital music typesetting toolkit for music ministries in Catholic parishes. The toolkit helps build musical arrangements around traditional hymns in Gregorian notation. As well as laying them out into documents, both for the congregation and the choir/musicians.

#### ETAB

https://github.com/guild-st-isidore-TO/editoristabularum

The Editoris Tabularum is a digital typesetting toolkit for creating documents like prayer booklets, mass and liturgical programs, parish announcements, etc.

#### ARCA

https://github.com/guild-st-isidore-TO/architectuscalculonis

The Architectus Calculonis is a parametric 2D/3D modelling toolkit that creates 2D designs and 3D models through Python scripts.
