# Typical device design workflow

Using blockspecs, a typical device design workflow would be as follows:

* From the product functional specification, identify sets of control functions that can logically be grouped into blocks.  These sets of functions might be:
  * Replicated in the device, as in the mixing console example above;
  * Already existing in other products (or expected to exist in future products);
  * Industry standard protocol interfaces.
* Create or find usable blockspec definitions.  Such definitions might be:
  * Defined in public blockspec libraries;
  * Defined in private (i.e. corporate) blockspec libraries;
  * Custom-built for the product being designed.
* If necessary, modify found blockspecs to fit requirements exactly.
* Create a new blockspec (`root blockspec`) for the device's root block that:
  * Instantiates all the component blockspecs as required, and
  * Defines individual control objects as needed (e.g. a power on/off control).
* Use the completed root blockspec to drive manual or automatic code generation processes to implement the device's NCA control API.
