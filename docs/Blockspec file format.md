# Blockspec file format

A blockspec file contains a single JSON object with one or two properties, as follows:

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ----------------- | --------------- |
| libraries | array (if the blockspec file contains no library identifiers, the library array may be omitted) | Library directory: Array of library identifiers used in the blockspec file and the URLs to which they correspond. A null URL implies that the location of the given library is the blockspec file itself. |
| blockspecs | array | Array of blockspecs. |
