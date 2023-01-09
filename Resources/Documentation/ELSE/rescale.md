---
title: rescale

description: Rescale MIDI values

categories:
 - object

pdcategory: Math

arguments:
- type: list
  description: 3 arguments: minimum output, maximum output, exponential factor. 5: minimum input, maximum input, minimum output, maximum output, exponential factor
  default: 0, 127, 0, 1, 1

inlets:
  1st:
  - type: float/list
    description: original value(s)
  - type: bang
    description: outputs the last rescaled float value
  nth:
  - type: float
    description: range parameters

outlets:
  1st:
  - type: float/list
    description: the rescaled value(s)

flags:
  - name: -clip
    description: sets clipping on

methods:
  - type: set
    description: sets the next value to be rescaled via bang
  - type: exp <float>
    description: sets the exponential factor
  - type: clip <float>
    description: 1 - clipping in, 0 - off

draft: false
---

By default, [rescale] rescales MIDI input values from 0 to 127 (including floats) into another range of values (0-1 by default). You can also set an exponential factor (1 by default - linear). All these parameters can be changed by arguments.