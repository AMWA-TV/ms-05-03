# Stereo audio gain with nested block

Here is a blockspec for a two-channel audio gain control block that includes a nested block that adjusts individual channel gains. This example also shows the use of the speclib library features, which include the specLibId property of the block member, and the Libraries table elsewhere in the document.

The block diagrams for the main block and nested block are as follows:

![Stereo Gain Block](images/StereoGainBlock.png)

![Channel Gain Block](images/ChannelGainBlock.png)

Here is the blockspec for the outer block, `StereoGainBlock`:

```json
{
    "specId": "StereoGainBlock",
    "specVersion": {
            "major": 1,
            "minor": 0,
            "patch": 0
    },
    "members": [
            {
                "role": "stereoGain",
                "specId": "ChannelGainBlock",
                "specVersion": 1234,
                "comment": "ncaBlock",
                "classId": [ 1, 1 ],
                "classVersion": {
                        "major": 1,
                        "minor": 0,
                        "patch": 0
                },
                "ports": [
                        {
                            "portName": "stereo_gain_input_1",
                            "direction": "input"
                        },
                        {
                            "portName": "stereo_gain_input_2",
                            "direction": "input"
                        },
                        {
                            "portName": "stereo_gain_output_1",
                            "direction": "output"
                        },
                        {
                            "portName": "stereo_gain_output_2",
                            "direction": "output"
                        }
                ],
                "constraints": [
                        {
                            "path": "left",
                            "propertyId": {
                                    "level": 4,
                                    "index": 1
                            },
                            "value": 0,
                            "minimum": -20,
                            "maximum": 0
                        },
                        {
                            "path": "right",
                            "propertyId": {
                                    "level": 4,
                                    "index": 1
                            },
                            "value": 0,
                            "minimum": -20,
                            "maximum": 0
                        }
                ]
            },
            {
                "role": "masterGain",
                "class": "ncaGain",
                "classId": [ 1, 2, 1, 1 ],
                "classVersion": {
                        "major": 1,
                        "minor": 0,
                        "patch": 0
                },
                "ports": [
                        {
                            "portName": "input_1",
                            "direction": "input"
                        },
                        {
                            "portName": "input_2",
                            "direction": "input"
                        },
                        {
                            "portName": "output_1",
                            "direction": "output"
                        },
                        {
                            "portName": "output_2",
                            "direction": "output"
                        }
                ],
                "constraints": [
                        {
                            "propertyId": {
                                    "level": 4,
                                    "index": 1
                            },
                            "value": -5,
                            "minimum": -50,
                            "maximum": 10
                        }
                ]
            }
    ],
    "ports": [
            {
                "portName": "block_input_1",
                "direction": "input"
            },
            {
                "portName": "block_input_2",
                "direction": "input"
            },
            {
                "portName": "block_output_1",
                "direction": "output"
            },
            {
                "portName": "block_output_2",
                "direction": "output"
            }
    ],
    "signalPaths": [
            {
                "source": {
                        "path": [],
                        "portName": "block_input_1"
                },
                "sink": {
                        "path": [ "stereoGain" ],
                        "portName": "stereo_gain_input_1"
                },
                "pathName": "path_1"
            },
            {
                "source": {
                        "path": [ "stereoGain" ],
                        "portName": "stereo_gain_output_1"
                },
                "sink": {
                        "path": [ "masterGain" ],
                        "portName": "input_1"
                },
                "pathName": "path_2"
            },
            {
                "source": {
                        "path": [ "masterGain" ],
                        "portName": "output_1"
                },
                "sink": {
                        "path": [],
                        "portName": "block_output_1"
                },
                "pathName": "path_5"
            },
            {
                "source": {
                        "path": [],
                        "portName": "block_input_2"
                },
                "sink": {
                        "path": [ "stereoGain" ],
                        "portName": "stereo_gain_input_1"
                },
                "pathName": "path_3"
            },
            {
                "source": {
                        "path": [ "stereoGain" ],
                        "portName": "stereo_gain_output_2"
                },
                "sink": {
                        "path": [ "masterGain" ],
                        "portName": "input_2"
                },
                "pathName": "path_4"
            },
            {
                "source": {
                        "path": [ "masterGain" ],
                        "portName": "output_2"
                },
                "sink": {
                        "path": [],
                        "portName": "block_output_2"
                },
                "pathName": "path_6"
            }
    ]
}
```

Here is the blockspec for the inner gain block, `ChannelGainBlock`:

```json
{
    "specId": "ChannelGainBlock",
    "specVersion": {
            "major": 1,
            "minor": 0,
            "patch": 0
    },
    "specLibId": "basicAudio",
    "specDescription": "Two-channel audio gain control",
    "lockable": true,
    "isDynamic": false,
    "ports": [
            {
                "role": "block_input_1",
                "direction": "input"
            },
            {
                "role": "block_input_2",
                "direction": "input"
            },
            {
                "role": "block_output_1",
                "direction": "output"
            },
            {
                "role": "block_output_2",
                "direction": "output"
            }
    ],
    "signalFlows": [
            {
                "source": {
                        "path": [],
                        "role": "block_input_1"
                },
                "sink": {
                        "path": [ "leftGain" ],
                        "role": "input_1"
                }
            },
            {
                "source": {
                        "path": [ "leftGain" ],
                        "role": "output_1"
                },
                "sink": {
                        "path": [],
                        "role": "block_output_1"
                }
            }
    ],
    "members": [
            {
                "role": "left",
                "comment": "ncaGain",
                "classId": [ 1, 2, 1, 1 ],
                "classVersion": 1,
                "constantOID": true,
                "ports": [
                        {
                            "role": "input_1",
                            "direction": "input"
                        },
                        {
                            "role": "output_1",
                            "direction": "output"
                        }
                ]
            },
            {
                "role": "right",
                "classId": [ 1, 2, 1, 1 ],
                "classVersion": 1,
                "comment": "ncaGain",
                "constantOID": true,
                "ports": [
                        {
                            "role": "input_1",
                            "direction": "input"
                        },
                        {
                            "role": "output_1",
                            "direction": "output"
                        }
                ]
            }
    ]
}
```

Here is the libraries table that goes at the beginning of the blockspec file and decodes library spec IDs mentioned in the blockspec:

```json
{
  "libraries": [
    {
      "reference": "stereoAudio",
      "location": "<AMWA repo link>"
    },
    {
      "reference": "basicAudio",
      "location": "<AMWA repo link>"
    }
  ]
}
```
