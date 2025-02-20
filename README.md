# Quake3Quest HD Textures
Upscaled HD texture packs designed specifically for use with the VR port of Quake 3, [Quake3Quest](https://quake3quest.quakevr.com/) by Team Beef.

## About this texture pack

This texture pack was upscaled using AI upscaling tool [RealESRGAN](https://github.com/xinntao/Real-ESRGAN) to upscale the original Quake 3 textures to 4x their original resolution. From that 4x version, smaller 3x and 2x scaled versions were also created for ideal performance on the Quest platform.

I created this pack because I tried some of the other Quake 3 HD texture packs out there, and found that the best looking one I could find ([Quake 3 Neural Upscale](https://www.moddb.com/mods/quake-3-neural-upscale) by MamiyaOtaru, released 2019) looks great but doesn't have great performance on Quake3Quest. The 4x upscale is a bit heavy on performance and can introduce a stutter to the game, in addition to crashing the game on 4 levels.

So, I set out to create a new upscale pack and found that using RealESRGAN, the results seem to come out nicer than the textures in the above linked pack which used waifu2x and SFTGAN.

Full disclosure: I know next to nothing about texture upscaling, I'm just a guy messing around with some things I found on Google. After giving it a shot I liked the results and found it fun to put together, so I'm publishing the texture pack for others to enjoy.

## Upscaling method & model used

For v0.2-beta, [RealESRGAN](https://github.com/xinntao/Real-ESRGAN) was used to create a 4x upscale of the original Quake 3 textures. Then, downscaling was used to create the 3x and 2x versions.

The model used for scaling is `realesrgan-x4plus` which seems to do a great job, albeit a bit darker than the original textures. A gamma boost of 20% was applied after the upscaling to restore the images closer to their original brightness levels.

For future versions, I'm testing a few other upscaling models and will update when they are ready for testing.

## Recommended version

Using the 3x upscale is recommended on Quest 3, and 2x upscale on Quest 2. Although, from my testing (playing at 90 fps), I think the Quest 2 can handle the 3x upscale also as I didn't notice any frame drops when using it, but your mileage may vary. All feedback is welcome!
