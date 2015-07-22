Description
===========

waifu2x filter for VapourSynth, based on the w2xc library. It runs on the first available environment of the following order:
* CUDA
* AMD OpenCL
* FMA
* AVX
* OpenCV filter2D


Note
====
The filter will generate .bin files at the same location of the model files for the first time it runs. Make sure that your executable has write permission to the folder of the model files. The filter still can run even without the .bin files generated, but the performance will degrade.


Usage
=====

    w2xc.Waifu2x(clip clip[, int noise=1, int scale=2, int block=512, bint photo=False, bint gpu=True])

* noise: Denoising level.
  * 0 = no denoising
  * 1 = weak denoising
  * 2 = strong denoising

* scale: Upscaling factor. Must be a power of 2. Set to 1 for no upscaling.

* block: The block size for dividing the image during processing. Smaller value results in lower VRAM usage, while larger value may give faster speed. It may be more efficient when the block size is a common divisor of the width and height.

* photo: When set to true, the photo model will be used for upscaling. Currently there are no photo models released for denoising yet, so the anime models will be used for denoising at the moment, which may give inferior results. When set to false, the anime models are used for both denoising and upscaling. There are two sets of models for anime, one is trained for RGB, the other is trained for Y (luma only). The RGB model is loaded when the color family of the input is RGB, and the Y (luma only) model is loaded for all the other color family. Note that photo model is only available for RGB, so this parameter has no effect for non-RGB input.

* gpu: Whether the calculation is done on GPU or CPU.


Dependencies
============
[w2xc](https://github.com/tanakamura/waifu2x-converter-cpp)
