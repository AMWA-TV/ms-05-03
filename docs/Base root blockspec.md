# Base root blockspec

The following blockspec definition must be implemented by any minimum compliant NCA device.
This blockspec must be applied to a device's root block as signaled by `"isRoot": true`.

The blockspec describes the minimum requirements for the `root block`.

It must contain the following managers:

* Device manager
* Class manager
* Subscription manager

Any other root blockspec must inherit from this base root blockspec.

```json
{
    "isRoot": true,
    "specId": "base-root",
    "specVersion": "1.0.0",
    "specDescription": "Blockspec for root block of minimum compliant device",
    "comment": "This blockspec definition must be implemented by any minimum compliant NCA device",
    "members": [
        {
            "role": "DeviceManager",
            "classId": [
                1,
                3,
                1
            ],
            "comment": "Device manager",
            "classVersion": "1.0.0"
        },
        {
            "role": "ClassManager",
            "classId": [
                1,
                3,
                2
            ],
            "comment": "Class manager",
            "classVersion": "1.0.0"
        },
        {
            "role": "SubscriptionManager",
            "classId": [
                1,
                3,
                4
            ],
            "comment": "Subscription manager",
            "classVersion": "1.0.0"
        }
    ]
}
```
