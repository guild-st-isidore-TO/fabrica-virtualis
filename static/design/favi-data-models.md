# FAVI Data Models

Back to [main README](../../README.md)

---

Common data formats understood by FAVI modules

## ENTITY MODELS

![FAVI data models](./favi-data-models.svg "FAVI data models")

### Generic File

Any kind of file

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Path** | string | yes | File's location in file system |
| **ID** | string | yes | String identifier used throughout system, sometimes in outputs. |
| **Tags** | string[] | no | List of tags for this file |

### Image File

EXTENDS **Generic File**  

PNG, JPG, SVG

### Document File

EXTENDS **Generic File**  

PDF, PS

### Text File

EXTENDS **Generic File**  

Flat text files, anything that can be edited in a text editor.

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Name** | string | no | Text document name |

---

### Markdown File

EXTENDS **Text File**  

Markdown files

`// TODO -- Add metadata/front-matter`

### GABC File

EXTENDS **Text File**  

GABC score files

`// TODO -- Add metadata`

### LilyPond File

EXTENDS **Text File**  

LilyPond score files

`// TODO -- Add metadata`

## FAVI MODELS

### EMEL Document

EXTENDS **LilyPond File**  

Documents hanlded by Editoris Melicorum

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Version** | string | no | Document version |

### ETAB Document

EXTENDS **Markdown File**  

Documents hanlded by Editoris Tabularum

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Version** | string | no | Document version |
