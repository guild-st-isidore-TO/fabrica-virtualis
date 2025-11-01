# Data Models

Back to [main README](../../README.md)

---

Common data formats understood by FaVirtu modules

## ENTITY MODELS

![FaVirtu data models](./img/favi-data-models-1.0.svg "FaVirtu data models")

### Generic File

Any kind of file

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Filename** | string | yes | File's name |
| **Directory** | string | yes | File's location in system |
| **Path** | string | yes | File's location and name |
| **Format** | string | yes | File extension / type |
| **ID** | string | yes | String identifier used throughout system, sometimes in outputs. |
| **Filestub** | string | yes | File's name without format extension |
| **Fileslug** | string | yes | Lowercase slug-ified version of Filestub |
| **FaViTags** | string[] | no | List of tags for this file |
| **FaViType** | string | no | FaVirtu document type |
| **FaViCategory** | string | no | FaVirtu document category |

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
| **Encoding** | string | no | Text encoding type |

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

## FaVirtu MODELS

### EdiMeli Document

EXTENDS **LilyPond File**  

Documents hanlded by Editoris Melicorum

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Version** | string | no | Document version |

### EdTab Document

EXTENDS **Markdown File**  

Documents hanlded by Editoris Tabularum

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| **Version** | string | no | Document version |
