# Shader Reference

Source route: `/docs/references/shader`. Media is not bundled; public route availability must be verified.

Shaders are written in **Metal**. See the [Shader Guide](shaders-guide.md) for a walkthrough.

## Default Shader

```metal
fragment float4 shader() {
	return float4(u, v, 0.0, 1.0);
}
```

![Default shader output: red and green coordinate gradient](https://flownodes.app/docs/media/shaders-reference/shader-1.png)

This returns a gradient Graphic, based on predefined `u` (x / width) and `v` (y / height) variables.

> **Note**
> The return value of type `float4` represents `RGBA` of the pixel at `u` and `v`. Keep the entry point exactly `fragment float4 shader()` with no arguments.

## Predefined Variables

- `u` is a `float` that goes horizontally in the X axis from `0.0` to `1.0`, left to right.
- `v` is a `float` that goes vertically in the Y axis from `0.0` to `1.0`, top to bottom.
- `uv` is a `float2`, a combination of `u` and `v`.
- `resolution` is a `float2` with the resolution of the output Graphic.
- `sampler` can be used to sample pixels in an input Graphic.
- `M_PI_F` PI (Defined by Metal).

> **Note**
> To access the `float2` components append `.x` or `.y`, and for a color’s `float4` components `.r`, `.g`, `.b`, `.a`.

## User Defined Variables

In the [Shader](../nodes/node-general-code-shader.json) node, custom variables and textures can be added via inlets.

In properties, use **External Inlets** to add the variables, along with names.

Once a variable is created, a new inlet will be added to the node.

## Sampling Pixel Colors

```metal
float4 color = graphic_1.sample(sampler, uv);
```

This code assumes there is an external inlet of type Graphic added with a name of `graphic_1`.

To get the resolution of the input Graphic, use the get functions like this:

```metal
uint inputWidth = graphic_1.get_width();
uint inputHeight = graphic_1.get_height();
```

## Custom Functions

```metal
float smooth(float value) {
    return cos(value * M_PI_F + M_PI_F) / 2.0 + 0.5;
}

fragment float4 shader() {
    return float4(smooth(u), smooth(v), 0.0, 1.0);
}
```

> **Warning**
> Custom functions need to be defined **above** the main `shader` function to compile. Pass any required coordinates or inlet values as function arguments; they are local to `shader()`.

## Official Docs

[Metal Shading Language Specification](https://developer.apple.com/metal/Metal-Shading-Language-Specification.pdf)
