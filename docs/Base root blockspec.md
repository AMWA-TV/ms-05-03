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
            "identity": {
                "id": [
                    1,
                    3,
                    1
                ],
                "version": "1.0.0"
            },
            "comment": "Device manager"
        },
        {
            "role": "ClassManager",
            "identity": {
                "id": [
                    1,
                    3,
                    2
                ],
                "version": "1.0.0"
            },
            "comment": "Class manager"
        },
        {
            "role": "SubscriptionManager",
            "identity": {
                "id": [
                    1,
                    3,
                    4
                ],
                "version": "1.0.0"
            },
            "comment": "Subscription manager"
        }
    ]
}
```
