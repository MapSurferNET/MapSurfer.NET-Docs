# Image Compositing Operators

## Introduction
In computer graphics, image compositing is a technique of combining two raster images to create a new resulting image. There are two different group of operations (modes): **alpha compositing** and **color blending**.

**Alpha compositing** (see [Porter and Duff](http://keithp.com/~keithp/porterduff/p253-porter.pdf)) is an operation which defines how two images are combined using only alpha components of the images.

**Color blending** is an operation which mixes the colors of two images by producing a new color.

In both modes, the first and the second colors presents the colors of the source and the destination images. 

This article provides the full list of compositing modes available in MapSurfer.NET. This list consists of 46 operations in total, 11 operations in the alpha compositing and 35 in the color blending group respectively. In MapSurfer.NET compositing operations can be applied to two types of the objects, namely to layers and styles.

In order to demonstrate the effect of each mode, we first give a short description of each operator and visually present a resulting image obtained by applying this operator to the pair of the following images (source and destination).

### Example Images
<center>![](/media/images/image_compositing/origin/Src1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/origin/Src2.png)</center>


<center>![](/media/images/image_compositing/origin/Dst1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/origin/Dst2.png)</center>


## Alpha Blending

### Source
The source is copied to the destination. 
<center>![](/media/images/image_compositing/Source_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Source_2.png)</center>

### SourceOver
The source is drawn on top of the destination. 
<center>![](/media/images/image_compositing/SourceOver_1.png)&nbsp;&nbsp;&nbsp;&nbsp; ![](/media/images/image_compositing/SourceOver_2.png)</center>

### SourceIn
The part of the source that overlaps the destination replaces the destination.
<center>![](/media/images/image_compositing/SourceIn_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/SourceIn_2.png)</center>
    
### SourceOut
The source is drawn on top of the destination only in regions where the destination is transparent.
<center>![](/media/images/image_compositing/SourceOut_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/SourceOut_2.png)</center>

### SourceATop
The source is drawn on top of the destination in regions where it intersects the destination.
<center>![](/media/images/image_compositing/SourceATop_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/SourceATop_2.png)</center>

### Destination
The destination is left unchanged, i.e. the source is not taken into account.
<center>![](/media/images/image_compositing/Destination_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Destination_2.png)</center>

### DestinationOver
The destination is drawn on top of the source. 
<center>![](/media/images/image_compositing/DestinationOver_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/DestinationOver_2.png)</center>

### DestinationIn 
The destination is drawn only in regions where it overlaps the source. 
<center>![](/media/images/image_compositing/DestinationIn_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/DestinationIn_2.png)</center>
    
### DestinationOut
The destination is drawn only in regions where the destination does not overlap the source. 
<center>![](/media/images/image_compositing/DestinationOut_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/DestinationOut_2.png)</center>
    
### DestinationATop
The destination is composited over the source in regions where it overlaps the source. Source is placed elsewhere.
<center>![](/media/images/image_compositing/DestinationATop_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/DestinationATop_2.png)</center>

### Xor
The Xor operator, also known as 'exclusive or', combines the non-overlapping regions of the source and the destination. 
<center>![](/media/images/image_compositing/Xor_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Xor_2.png)</center>

## Color Blending

### Clear
Both the color values and the alpha of the destination are cleared.
<center>![](/media/images/image_compositing/Clear_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Clear_2.png)</center>

### Plus
The source is added to the destination and replaces the destination. This operator is useful for animating a dissolve between two images.
<center>![](/media/images/image_compositing/Plus_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Plus_2.png)</center>

### Minus
Adds the values of the source and base colors and subtracts 255 from the result. Because this merge mode treats the color channels as subtractive, the result color is never lighter than the base color. 
<center>![](/media/images/image_compositing/Minus_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Minus_2.png)</center>

### Multiply
<center>![](/media/images/image_compositing/Multiply_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Multiply_2.png)</center>

### Screen
Multiplies the complements of the destination and source color values, then complements the result. The result color is always at least as light as either of the two constituent colors. Screening any color with white produces white; screening with black leaves the original color unchanged. The effect is similar to projecting multiple photographic slides simultaneously onto a single screen.
<center>![](/media/images/image_compositing/Screen_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Screen_2.png)</center>

### Overlay 
<center>![](/media/images/image_compositing/Overlay_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Overlay_2.png)</center>

### Darken
Returns the darker of the source and the destination colors. The destination is replaced with the source when the source is darker, otherwise it is left unchanged.
<center>![](/media/images/image_compositing/Darken_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Darken_2.png)</center>

### Lighten
Returns the lighter of the source and the destination colors. The destination is replaced with the source when the source is lighter, otherwise it is left unchanged.
<center>![](/media/images/image_compositing/Lighten_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Lighten_2.png)</center>

### ColorDodge
Brightens the destination color to reflect the source color. Painting with black produces no change.
<center>![](/media/images/image_compositing/ColorDodge_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/ColorDodge_2.png)</center>

### ColorBurn
Darkens the destination color to reflect the source color. Painting with white produces no change.
<center>![](/media/images/image_compositing/ColorBurn_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/ColorBurn_2.png)</center>

### HardLight
Multiplies or screens the colors, dependent on the source color value. If the source color is lighter than 0.5, the destination is lightened as if it were screened. If the source color is darker than 0.5, the destination is darkened, as if it were multiplied. The degree of lightening or darkening is proportional to the difference between the source color and 0.5. If it is equal to 0.5 the destination is unchanged. Painting with pure black or white produces black or white.
<center>![](/media/images/image_compositing/HardLight_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/HardLight_2.png)</center>

### SoftLight
Darkens or lightens the colors, dependent on the source color value. If the source color is lighter than 0.5, the destination is lightened. If the source color is darker than 0.5, the destination is darkened, as if it were burned in. The degree of darkening or lightening is proportional to the difference between the source color and 0.5. If it is equal to 0.5, the destination is unchanged. Painting with pure black or white produces a distinctly darker or lighter area, but does not result in pure black or white.
<center>![](/media/images/image_compositing/SoftLight_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/SoftLight_2.png)</center>

### Difference
Subtracts the darker of the two constituent colors from the lighter. Painting with white inverts the destination color. Painting with black produces no change.
<center>![](/media/images/image_compositing/Difference_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Difference_2.png)</center>

### Exclusion
Produces an effect similar to that of **Difference**, but appears as lower contrast. Painting with white inverts the
destination color. Painting with black produces no change.
<center>![](/media/images/image_compositing/Exclusion_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Exclusion_2.png)</center>

### Contrast
<center>![](/media/images/image_compositing/Contrast_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Contrast_2.png)</center>

### Invert
<center>![](/media/images/image_compositing/Invert_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Invert_2.png)</center>

### InvertRGB 
<center>![](/media/images/image_compositing/InvertRGB_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/InvertRGB_2.png)</center>

### GrainMerge
<center>![](/media/images/image_compositing/GrainMerge_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/GrainMerge_2.png)</center>

### GrainExtract
<center>![](/media/images/image_compositing/GrainExtract_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/GrainExtract_2.png)</center>

### Hue 
<center>![](/media/images/image_compositing/Hue_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Hue_2.png)</center>

### Saturation
<center>![](/media/images/image_compositing/Saturation_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Saturation_2.png)</center>

### Color 
<center>![](/media/images/image_compositing/Color_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Color_2.png)</center>

### Value
<center>![](/media/images/image_compositing/Value_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Value_2.png)</center>

### LinearDodge
<center>![](/media/images/image_compositing/LinearDodge_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/LinearDodge_2.png)</center>

### LinearBurn
<center>![](/media/images/image_compositing/LinearBurn_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/LinearBurn_2.png)</center>

### VividLight
<center>![](/media/images/image_compositing/VividLight_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/VividLight_2.png)</center>

### LinearLight
<center>![](/media/images/image_compositing/LinearLight_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/LinearLight_2.png)</center>

### PinLight
Replaces the colors, depending on the blend color. If the blend color (light source) is lighter than 50% gray, pixels darker than the blend color are replaced, and pixels lighter than the blend color do not change. If the blend color is darker than 50% gray, pixels lighter than the blend color are replaced, and pixels darker than the blend color do not change. This is useful for adding special effects to an image.
<center>![](/media/images/image_compositing/PinLight_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/PinLight_2.png)</center>

### HardMix 
<center>![](/media/images/image_compositing/HardMix_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/HardMix_2.png)</center>

### Glow 
<center>![](/media/images/image_compositing/Glow_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Glow_2.png)</center>

### Reflect 
<center>![](/media/images/image_compositing/Reflect_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Reflect_2.png)</center>

### Freeze
<center>![](/media/images/image_compositing/Freeze_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Freeze_2.png)</center>

### Heat 
<center>![](/media/images/image_compositing/Heat_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Heat_2.png)</center>

### Phoenix
<center>![](/media/images/image_compositing/Phoenix_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Phoenix_2.png)</center>

### Stamp
<center>![](/media/images/image_compositing/Stamp_1.png)&nbsp;&nbsp;&nbsp;&nbsp;![](/media/images/image_compositing/Stamp_2.png)</center>


