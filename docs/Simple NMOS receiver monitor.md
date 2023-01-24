# Simple NMOS receiver monitor

The following is a blockspec for a simple NMOS receiver monitor. The block contains only one object, an instance of the `NcReceiverMonitor` class. In this case, the block doesn't process any media signals, so neither it nor the object it contains has any ports, and there are no signal paths.

```json
{
    "specId": "receiver-status",
    "specVersion": "1.0.0",
    "specDescription": "Blockspec for receiver status",
    "comment": "A blockspec for a simple NMOS receiver monitor",
    "members": [
        {
            "role": "ReceiverMonitor_01",
            "classId": [1, 2, 3],
            "comment": "Receiver monitor",
            "classVersion": "1.0.0"
        }
    ]
}
```
