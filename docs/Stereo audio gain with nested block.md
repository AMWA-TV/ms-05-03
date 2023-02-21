# Stereo audio gain with nested block

The following is a blockspec for a two-channel audio gain control block that includes a nested block that adjusts individual channel gains. This example also shows the use of the speclib library features, which include the specLibId property of the block member, and the Libraries table elsewhere in the document.

The block diagrams for the main block and nested block are as follows:

![Stereo Gain Block](images/StereoGainBlock.png)

![Channel Gain Block](images/ChannelGainBlock.png)

Here is the blockspec for the outer block, `StereoGainBlock`:

```json
{
    "specId": "StereoGainBlock",
    "specVersion": "1.0.0",
    "specDescription": "Stereo gain block spec",
    "members": [
        {
            "role": "stereoGain",
            "specId": "ChannelGainBlock",
            "specVersion": "1.0.0",
            "comment": "NcBlock",
            "classId": [ 1, 1 ],
            "ports": [
                {
                    "role": "stereo_gain_input_1",
                    "direction": "input"
                },
                {
                    "role": "stereo_gain_input_2",
                    "direction": "input"
                },
                {
                    "role": "stereo_gain_output_1",
                    "direction": "output"
                },
                {
                    "role": "stereo_gain_output_2",
                    "direction": "output"
                }
            ],
            "constraints": [
                {
                    "path": [ "left" ],
                    "propertyId": {
                        "level": 5,
                        "index": 1
                    },
                    "comment": "NcGain gainValue property",
                    "minimum": -20,
                    "maximum": 0
                },
                {
                    "path": [ "right" ],
                    "propertyId": {
                        "level": 5,
                        "index": 1
                    },
                    "comment": "NcGain gainValue property",
                    "minimum": -20,
                    "maximum": 0
                }
            ]
        },
        {
            "role": "masterGain",
            "classId": [ 1, 2, 1, 1, 1 ],
            "ports": [
                {
                    "role": "input_1",
                    "direction": "input"
                },
                {
                    "role": "input_2",
                    "direction": "input"
                },
                {
                    "role": "output_1",
                    "direction": "output"
                },
                {
                    "role": "output_2",
                    "direction": "output"
                }
            ],
            "constraints": [
                {
                    "path": null,
                    "propertyId": {
                        "level": 5,
                        "index": 1
                    },
                    "comment": "NcGain gainValue property",
                    "minimum": -50,
                    "maximum": 10
                }
            ]
        }
    ],
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
    "signalPaths": [
        {
            "source": {
                "owner": [],
                "role": "block_input_1"
            },
            "sink": {
                "owner": [ "stereoGain" ],
                "role": "stereo_gain_input_1"
            },
            "role": "owner_1"
        },
        {
            "source": {
                "owner": [ "stereoGain" ],
                "role": "stereo_gain_output_1"
            },
            "sink": {
                "owner": [ "masterGain" ],
                "role": "input_1"
            },
            "role": "owner_2"
        },
        {
            "source": {
                "owner": [ "masterGain" ],
                "role": "output_1"
            },
            "sink": {
                "owner": [],
                "role": "block_output_1"
            },
            "role": "owner_5"
        },
        {
            "source": {
                "owner": [],
                "role": "block_input_2"
            },
            "sink": {
                "owner": [ "stereoGain" ],
                "role": "stereo_gain_input_1"
            },
            "role": "owner_3"
        },
        {
            "source": {
                "owner": [ "stereoGain" ],
                "role": "stereo_gain_output_2"
            },
            "sink": {
                "owner": [ "masterGain" ],
                "role": "input_2"
            },
            "role": "owner_4"
        },
        {
            "source": {
                "owner": [ "masterGain" ],
                "role": "output_2"
            },
            "sink": {
                "owner": [],
                "role": "block_output_2"
            },
            "role": "owner_6"
        }
    ]
}
```

Here is the blockspec for the inner gain block, `ChannelGainBlock`:

```json
{
    "specId": "ChannelGainBlock",
    "specVersion": "1.0.0",
    "specLibId": "basicAudio",
    "specDescription": "Two-channel audio gain control",
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
                "owner": [],
                "role": "block_input_1"
            },
            "sink": {
                "owner": [ "leftGain" ],
                "role": "input_1"
            }
        },
        {
            "source": {
                "owner": [ "leftGain" ],
                "role": "output_1"
            },
            "sink": {
                "owner": [],
                "role": "block_output_1"
            }
        }
    ],
    "members": [
        {
            "role": "left",
            "comment": "NcGain",
            "classId": [ 1, 2, 1, 1, 1 ],
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
            "classId": [ 1, 2, 1, 1, 1 ],
            "comment": "NcGain",
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

Here is the libraries collection that goes at the beginning of the blockspec file and decodes library spec IDs mentioned in the blockspec:

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
