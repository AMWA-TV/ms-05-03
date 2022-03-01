# Simple NMOS receiver monitor

Here is a blockspec for a simple NMOS receiver monitor.  The block contains only one object, an instance of the `ncReceiverMonitor` class. In this case, the block doesn't process any media signals, so neither it nor the object it contains has any ports, and there are no signal paths.

```json
{
    "specId": "ReceiverStatusBlock",
    "specVersion": {"major":2, "minor":0, "patch":0},
    "ports": [],
    "signalPaths": [],
    "members": [
        {
            "role": "receiverStatus",
            "classId": [1,4,1,1],
            "comment": "ncReceiverMonitor",
            "classVersion": {"major":1,"minor":0, "patch":0},
            "ports": []
        }
    ]
}
```
