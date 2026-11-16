# Pixel Particles Guide

Source route: `/docs/guides/pixel-particles`. Media is not bundled; public route availability must be verified.

![Pixel Particles — step 1](https://flownodes.app/docs/media/guides-pixel-particles/media-01.png)

> This guide was made on Mac, tho it’s also compatible with iPhone, iPad and Vision Pro.

> This guide requires the [Pixel Particles](../nodes/graphic/system.json) (`node:graphic:system:pixelParticles`) that is available in the Visuals & Effects bundle.

Create 1’000’000 particles via a graphic with resolution 1’000 x 1’000.  

[Video guide](https://www.youtube.com/watch?v=L1PSNhrZutY)

## The Pixel Particles Node

Start with a blank canvas, a new Flow:

![Pixel Particles — step 2](https://flownodes.app/docs/media/guides-pixel-particles/media-02.png)

Add the Pixel Particles node:

![Pixel Particles — step 3](https://flownodes.app/docs/media/guides-pixel-particles/media-03.png)

Note that there is a connection error. This is expected. We need to provide pixel particle locations.

![Pixel Particles — step 4](https://flownodes.app/docs/media/guides-pixel-particles/media-04.png)

## The Grid - Gradient Nodes

One pixel becomes one particle, Red is X and Green is Y. So to spread out the particles in a grid we will use two gradients to create a “UV” map.

Start by adding a [Gradient](../nodes/graphic/solid.json) (`node:graphic:solid:gradient`):

![Pixel Particles — step 5](https://flownodes.app/docs/media/guides-pixel-particles/media-05.png)

Color it black to green. Open the color stops and enter the RGB values. It’s important that it’s a pure green:

![Pixel Particles — step 6](https://flownodes.app/docs/media/guides-pixel-particles/media-06.png)

Duplicate it and make the new copy horizontal and black to red:

![Pixel Particles — step 7](https://flownodes.app/docs/media/guides-pixel-particles/media-07.png)

## The Grid - Blending

Blend the two nodes with “Add” blending mode:

![Pixel Particles — step 8](https://flownodes.app/docs/media/guides-pixel-particles/media-08.png)

Set the gradients to be 32 bit, this is needed to allow particles to be positioned accurately:

![Pixel Particles — step 9](https://flownodes.app/docs/media/guides-pixel-particles/media-09.png)

## The Grid - Transform with Light

Connect the blended gradients to the Pixel Particles node:

![Pixel Particles — step 10](https://flownodes.app/docs/media/guides-pixel-particles/media-10.png)

The grid is offset, this is because the colors go from 0.0 to 1.0 in X & Y, tho the center is zero.

To offset pixel particles, we use an exposure offset with a [Levels](../nodes/graphic/colorEffect.json) (`node:graphic:colorEffect:levels`). Offset by `-0.5`:

![Pixel Particles — step 11](https://flownodes.app/docs/media/guides-pixel-particles/media-11.png)

Now the grid should show, tho it’s a bit bright, so lower the alpha in the Pixel Particles node:

![Pixel Particles — step 12](https://flownodes.app/docs/media/guides-pixel-particles/media-12.png)

## The Wave - Noise

Add a [Noise](../nodes/graphic/solid.json) (`node:graphic:solid:noise`) and enable the Color property:

![Pixel Particles — step 13](https://flownodes.app/docs/media/guides-pixel-particles/media-13.png)

Make sure it’s 32 bit:

![Pixel Particles — step 14](https://flownodes.app/docs/media/guides-pixel-particles/media-14.png)

## The Wave - Cross

Add a [Cross](../nodes/graphic/modifierEffect.json) (`node:graphic:modifierEffect:cross`) and connect the blended gradients with the noise:

![Pixel Particles — step 15](https://flownodes.app/docs/media/guides-pixel-particles/media-15.png)

## Animation - Stopwatch

Add a [Stopwatch](../nodes/general/time.json) (`node:general:time:stopwatch2`) and connect it to the Depth Offset of the Noise:

![Pixel Particles — step 16](https://flownodes.app/docs/media/guides-pixel-particles/media-16.png)

Set the speed to 100 or 1000, and enable the Running property:

![Pixel Particles — step 17](https://flownodes.app/docs/media/guides-pixel-particles/media-17.png)

Now the pixel particles should animate:

![Pixel Particles — step 18](https://flownodes.app/docs/media/guides-pixel-particles/media-18.png)

The final look:

![Pixel Particles — step 19](https://flownodes.app/docs/media/guides-pixel-particles/media-19.png)

Here’s the flow file:

[Pixel_Particles.flow](https://flownodes.app/docs/media/guides-pixel-particles/media-20.flow)
