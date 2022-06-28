# Member specifications

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ------------------------------ | ----------------------------------------------------------|
| members           | array of member objects        | One array entry for each control object in the block      |

Each `members` entry is an object with the following properties:

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ------------------------------ | ---------------------------------------------------------------------------------------------|
| *Required properties for all control objects*      | |                                                                                            |
| role              | string                         | Role of object in containing block. Unique in containing block                               |
| classId           | string array                   | Class identity                                                                               |
| classVersion      | string                         | Version number of this object's class; format is defined by datatype `NcVersionCode`         |
| constantOid       | boolean                        | TRUE if and only if object ID is nonvolatile                                                 |
| *Optional property to be specified when the blockspec defines signal paths and when the member is a port-flexible object - see Ports section* | | |
| ports             | array of NcPort objects        | List of this object's NcPorts                                                                |
| *Optional additional properties to set values of other control object properties, where needed* | |                                               |
| (any)             | (varies)                       | Value of control object property                                                             |

## Nested blocks

A block is an NCA control object therefore, a blockspec defines a nested block by making it an item in the `members` array. Nested blocks have all the properties mentioned in the previous section but also add the following additional properties:

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ------------------------------ | ---------------------------------------------------------------------------------------------|
| specID            | string                         | Global ID of the blockspec that defines this nested block                                    |
| specVersion       | number                         | Version number of the blockspec                                                              |
| specLibraryID     | string                         | ID of library (optional)                                                                     |
