# Description

SangNom is a single field deinterlacer using edge-directed interpolation but nowadays it's mainly used in anti-aliasing scripts.

This is [a port of the VapourSynth plugin SangNom2](https://github.com/dubhater/vapoursynth-sangnom).

# Usage

```
SangNom2(clip, int "order", int "aa", int "aac", int "threads", bool "dh" , bool "luma", bool "chroma")
```

## Parameters:

- clip\
    A clip to process. It must be Y/YUV 8..32-bit format.
    
- order\
    0: Double frame rate, top and bottom fields are kept but DoubleWeave must be called before SangNom2.\
    1: Single frame rate, keep top field.\
    2: Single frame rate, keep bottom field.\
    Default: 1.
    
- aa\
    The strength of luma anti-aliasing, this value is considered in 8 bit clip.\
    Must be between 0 and 128.\
    Default: 48.
    
- aac\
    The strength of chroma anti-aliasing, this value is considered in 8 bit clip.\
    Must be between 0 and 128.\
    Default: 0.
    
- threads\
    It's a dummy parameter for backward compatibility.

- dh\
    Doubles the height of the input. Each line of the input is copied to every other line of the output and the missing lines are interpolated.\
    Note: If dh = true, it will force all planes to be processed.\
    Default: False.
    
- luma, chroma\
    Planes to process.\
    Default: luma=true; chroma = true.
    
# Lincese

This project is licensed under the MIT license. Binaries are GPL v2.