# Root block

Every NCA device model has a single `root block` that contains all the device's control objects. Control objects may be contained directly in the root block, or indirectly as contents of additional blocks contained (`nested`) in the root block. Blocks may be nested to any level.

Every control object has a `role` name that is unique within its containing block.

Control objects nested at any level inside the device model are uniquely identifiable using a role name path built from the roles of all the parents starting with the `root block` and finishing with the role of the specific control object.
