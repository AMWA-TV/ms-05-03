# Member specifications

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ------------------------------ | ----------------------------------------------------------|
| members           | array of member objects        | One array entry for each control object in the block      |

Each `members` entry is an object with the following properties:

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ------------------------------ | ---------------------------------------------------------------------------------------------|
| *Required properties for all control objects*      | |                                                                                            |
| role              | string                         | Role of object in containing block. Unique in containing block                               |
| class             | string                         | Name of this object's class                                                                  |
| classVersion      | string                         | Version number of this object's class; format is defined by datatype `ncaVersionCode`        |
| constantOid       | boolean                        | TRUE if and only if object ID is nonvolatile                                                 |
| *Optional property to be specified when the blockspec defines signal paths and when the member is a port-flexible object - see Ports section* | | |
| ports             | array of ncaPort objects       | List of this object's ncaPorts                                                               |
| *Optional additional properties to set values of other control object properties, where needed* | |                                               |
| (any)             | (varies)                       | Value of control object property                                                             |

## Nested blocks

As noted above, a block is an NCA control object. Therefore, a blockspec defines a nested block by making it an item in the `members` array. The contents of a nested block's `members` item are as follows (note there is no Ports item. This is explained in the `Ports` section):

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ------------------------------ | ---------------------------------------------------------------------------------------------|
| *Required properties*      | |                                                                                                                    |
| role              | string                         | Role of nested block in containing block. Unique in containing block                         |
| class             | string                         | Name of this object's class. Value = "ncaBlock"                                              |
| classVersion      | string                         | Version number of the current ncaBlock class                                                 |
| *Additional properties for nested blocks* | |                                                                                                     |
| specID            | string                         | Global ID of the blockspec that defines this nested block                                    |
| specVersion       | number                         | Version number of the blockspec                                                              |
| specLibraryID     | string                         | ID of library (optional)                                                                     |
