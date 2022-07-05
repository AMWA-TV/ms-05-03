# Base device blockspec

The following blockspec definition must be implemented by any minimum compliant NCA device.
This blockspec must be applied to a device's root block as signaled by `"isRoot": true`.

The blockspec describes the minimum requirements for the `root block`.

It must contain the following managers:

* Device manager
* Class manager
* Subscription manager

It must also be lockable as signaled by `"lockable": true`.
More information about the locking mechanisms is available in [MS-05-02 NMOS Control Framework](https://specs.amwa.tv/ms-05-02).

```json
{
    "isRoot": true,
    "specId": "minimum-device",
    "specVersion": "1.0.0",
    "specDescription": "Blockspec for root block of minimum device model",
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
                3
            ],
            "comment": "Class manager",
            "classVersion": "1.0.0"
        },
        {
            "role": "SubscriptionManager",
            "classId": [
                1,
                3,
                5
            ],
            "comment": "Subscription manager",
            "classVersion": "1.0.0"
        }
    ],
    "lockable": true
}
```
