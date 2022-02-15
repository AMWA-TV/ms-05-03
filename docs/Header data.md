# Header data

| **Property Name** | **JSON Datatype** | **Description** |
| ----------------- | ----------------- | ---------------------------------------------------------------------------|
| specId            | string            | Global ID of this blockspec                                                |
| specVersion       | number            | Version number of this blockspec                                           |
| parentSpecId      | string            | Global ID of this blockspec's parent                                       |
| parentSpecVersion | number            | Version number of this blockspec's parent                                  |
| specDescription   | string            | Simple description of this blockspec                                       |
| lockable          | boolean           | TRUE if and only if block may be locked by controllers                     |
| isDynamic         | boolean           | TRUE if and only if controllers may add and delete objects from this block |
