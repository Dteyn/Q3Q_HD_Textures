# Quake3Quest HD Textures
Upscaled HD texture packs designed specifically for use with the VR port of Quake 3, [Quake3Quest](https://quake3quest.quakevr.com/) by Team Beef.

# Status: Beta

***This project is currently in Beta status - more testing and feedback is needed before final release. All feedback is welcome!***

## Current Version: [v0.3-beta](https://github.com/Dteyn/Q3Q_HD_Textures/releases/tag/v0.3-beta)

### 2x upscale: (recommended for Quest 2)
- [zzz_Q3Q_HD_Upscale-2x-v03b.pk3](https://github.com/Dteyn/Q3Q_HD_Textures/releases/download/v0.3-beta/zzz_Q3Q_HD_Upscale-2x-v03b.pk3)

### 3x upscale: (recommended for Quest 3)
- [zzz_Q3Q_HD_Upscale-3x-v03b.pk3](https://github.com/Dteyn/Q3Q_HD_Textures/releases/download/v0.3-beta/zzz_Q3Q_HD_Upscale-3x-v03b.pk3)

A 4x upscale pack is also available for testing in the [Releases](https://github.com/Dteyn/Q3Q_HD_Textures/releases/tag/v0.3-beta) section. The 4x pack is still undergoing testing to ensure stable FPS, so the 2x and 3x packs above are recommended for most users for the time being.

## Installation

To install, simply download one of the above packs and drop it into your `ioquake3Quest/baseq3` folder and you should be good to go.

## About this texture pack

This texture pack was upscaled using AI upscaling tool [chaiNNer](https://github.com/chaiNNer-org/chaiNNer) to upscale the original Quake 3 textures to 4x their original resolution. From that 4x version, smaller 3x and 2x scaled versions were also created for ideal performance on the Quest platform.

I created this pack because I tried some of the other Quake 3 HD texture packs out there, and found that the best looking one I could find ([Quake 3 Neural Upscale](https://www.moddb.com/mods/quake-3-neural-upscale) by MamiyaOtaru, released 2019) looks great but doesn't have great performance on Quake3Quest. The 4x upscale is a bit heavy on performance and can introduce a stutter to the game, in addition to crashing the game on 4 levels.

So, I set out to create a new upscale pack and found that using RealESRGAN, the results seem to come out nicer than the textures in the above linked pack which used waifu2x and SFTGAN.

In version 0.3, I switched to using chaiNNer (previously was using RealESRGAN NCNN Vulkan edition) which has opened up a lot more possibility in models. I'm still testing models to see which one may have the best results, to feel free to test earlier versions as the textures may look slightly different with different upscaling methods. My goal is to find the one best suited to Quake 3 textures, which may take multiple attempts.

## Upscaling method & model used

For most textures, this is the method used for v0.3-beta:

  - Split Transparency (for images that have it):
    - RGB - Upscale Image pass 1 (4x):
          Model A: [4xTextureDAT2_otf](https://openmodeldb.info/models/4x-TextureDAT2-otf)
	- Upscale Image pass 2 (2x):
		  Model: [2x-realesrgan-x2plus](https://openmodeldb.info/models/2x-realesrgan-x2plus)
    - Downscale Image 50%
    - Alpha - Upscale Image pass 1 (4x):
            Model: [4x-1ch-Alpha-Lite](https://openmodeldb.info/models/4x-1ch-Alpha-Lite)
   - Average Color Fix  (NOTE: switching to Wavelet Color Fix in future attempts)
   - Merge Transparency

For face textures, a different model was used:
  - Split Transparency:
    - RGB: - Upscale Image pass 1 (4x):
          Interpolate Model: 25% A, 75% B
          Model A: [4xLSDIRDAT](https://openmodeldb.info/models/4x-LSDIRDAT)
		  Model B: [4xFaceUpDAT](https://openmodeldb.info/models/4x-FaceUpDAT)
	- Upscale Image pass 2 (1x):
		  Model: [GFPGANv1.4](https://github.com/TencentARC/GFPGAN)
    - Alpha - Upscale Image pass 1 (4x):
            Model: [4x-1ch-Alpha-Lite](https://openmodeldb.info/models/4x-1ch-Alpha-Lite)
   - Merge Transparency

For future versions, I'm testing a few other upscaling models and will update when they are ready for testing.

## Recommended version

Using the 3x upscale is recommended on Quest 3, and 2x upscale on Quest 2. Although, from my testing (playing at 120 fps), I think the Quest 2 can handle the 3x upscale also as I didn't notice any frame drops when using it, but your mileage may vary. I've also been testing the 4x pack on Quest 3 and it seems to perform okay, but more testing is needed across more levels.

All feedback is welcome! Feel free to open an [issue](https://github.com/Dteyn/Q3Q_HD_Textures/issues) if you run into any troubles or have suggestions for improvement. I can also be found on the Team Beef Discord server.
