# Gramp Icon Theme Guidelines


## Introduction
The Gramps icon theme's goal is to create a distinctive theme guide for Gramps icons. A user running a multiplatform application should not have the impression that the look is unpolished and incosistent with what he or she is used to. While this isn't about merging styles of all desktop systems, we do aim to not be drastically different on each platform.

Along with a generic type fallback, having a similar style will help in the transition phase with some legacy icons which may still remain on a user's particular desktop.

## Color Palette
<p align="center">
  <img src="https://github.com/bjpcorp/GTheme/blob/main/Gramps_Icon_Theme_Guidelines/gramps-colour-palette.png" width="80%" title="Gramps Colour Palette">
</p>
Having a common color palette is required to have a consistant look across all icons. Visual style is heavily influenced by the colors used.

The Gramps color palette consists of 27 RGB colors, based on the Tango palette, as shown on the image above. Most desktops allow for 24-bit RGB icons (+8-bit Alpha channel).

The common practice when drawing icons is to use the palette as a base, applying it on large areas. Shading with gradients, creating highlight and shadows by changing value, and minor changes of saturation are also allowed and endorsed. Colors do not have to come exclusively from this set, as additional colors may be used. Starting from the base color and changing value, saturation or even hue slightly gives more consistant results that starting from arbitrary colors.

***Note the latest development version of GIMP and Inkscape ship the Tango palette by default***.

## Defining Gramps Style Elements
There are many attributes of an icon that define it as part of Gramps, including ones such as perspective and lighting (which are outlined below).

Let's examine at the key visual aspects that define the style:

### 1. Object Outline
All Gramps icons are stroked with a thin outline to improve contrast. At low resolutions the stroke size is 1px. The stroke should not scale along with the icon, it should remain 1px.
The color of the outline is a dark variant of the key color of the icon. This is done by retaining the hue and saturation of the dominant fill color and lowering the value to approximately 20%). In the example above, the trashcan is green, so the stroke will be green as well.

### 2. Highlights
The edges of objects tend to reflect light more due to the fact the position of the observer relative to the light source is almost always ideal for the reflection. In terms of highlights, the theme inherits the style of Tango, Firefox/Thunderbird, Pinstripe/Winstripe designed by Kevin Gerich & Stephen Horlander (Pinstripe, Winstripe) which shift away from reality by creating a second inner outline of the object. This stroke is very subtle and may not be apparent on some matte objects.

### 3. Glossy Reflections
Use glossy reflection only on objects that have a reflective surface in real life (plastic, glass, some metal, et cetera). A sheet of paper certainly doesn't have such attribute.
Various elements have been picked from existing icon styles: Similar perspective as GNOME icons, a colored object stroke from KDE, an Aqua-like highlight influenced by Mac OS X, and edge highlights and overall lightness from the Firefox Pinstripe theme.

## Style Attributes
To better understand the style of Tango, consider the following adjectives:

- Light
- Crisp
- Straight
- Simplified
- Modern
- Well-balanced


## Perspective

There are three types of perspective defined for Gramps.

### 1. Flat/On the Shelf Perspective
This style resembles looking at an object on a shelf at eye level, looking at an object from above, or laying on surface. This is the most common perspective for toolbar icons and document mime type icons.

### 2. On the Table
This type of perspective is the most common for application icons. Action/Toolbar icons also utilize this perspective from time to time.

### 3. Tilted Table
In cases where the object's appearance is more evident from an angle, you are free to use the tilted table perspective—but this is the least common perspective of the three and should be used only in cases where the other two do not provide a clearly distinctive silhouette of the object.


## Lighting
Having homogenous lighting across all icons also is important for visual consistency. Tango icons are lit from above, with the light source slightly to the left. Icons with on the table perspective may cast a fuzzy shadow on the surface as if the light source came from the position of the observer.

## Sizes
There are 4 major icon sizes defined that an icon theme should contain: Large, Medium, Small and Extra Small. Each of these sizes needs to be treated separately, simple scaling of a larger icon doesn't work and ends up looking fuzzy and unclear. On top of that, a new optional size, X-Large, has been introduced.

### - Large
This size is mainly used for desktop icons and in the file manager views. The bitmap size is 48×48 pixels.
### - Medium
A very common size of 32x32px is used on some menus (slab) and very common on Windows.
### - Small
"Small" is the common size for application toolbar icons.

Its bitmap size is 22×22 pixels. This size is common for toolbars in KDE and the GIMP.

Gnome has been using a size of 24×24px (which is ¼ of 48×48); just adding a 1 pixel empty space on all sides can make Tango icons useful on the Gnome desktop. One can easily do this with imagemagick:

### - X-Small
At 16×16 pixels, the "Extra Small" size is used in places such as lists (file dialog, message list in an e-mail client, etc.) and menus.
### - X-Large
This size has been introduced fairly recently and is optional. Unless you are an experienced icon designer, do not start with this size as it goes against most of the good practice for icon design. You will be required to add insane amounts of detail and might end up with an unclear and complex metaphor. The canvas size is 256x256px and unlike all the other sizes, this artwork can be scaled from 49px up. In other words -- do not aim for pixel perfection here.
This size also holds another exception to the rule of stroking. Do not stroke x-large icons with the 1px common everywhere. In Inkscape we use a trick that achieves a similar contrast enhancing effect without losing upwards scalability. You create an outline object with no fill and a stroke of 3px. Then you duplicate such object and use the copy to clip itself. After blurring the object, the inside of the silhouette gets nicely shaded, while the outside is crisp. Instead of the inner stroke, use path shapes. Blur is a useful tool here as well.


## Common Filenaming
Until now, there has not been a standard for naming conventions. This resulted in themes which have not worked globally, as individual projects have used different names for the same icon.

Tango solves this issue with a Standard Icon Naming Specification

In the short term, existing KDE and GNOME icons names will be addressed using symlinks. We have prepared a script which automatically generates appropriate symlinks for existing naming schemes in GNOME and KDE so that compatibility with current desktop applications will be preserved.

## Metainformation
To make it easier for developers to search for icons in the Tango set, please provide keywords in the icon file. For example, appropriate keywords for a joystick icon are: controller, joystick, game, gaming, HID.

For SVG icons, the metainformation is written using the Dublin Core namespace.

Inkscape users can conveniently enter the data in the document properties (Ctrl+Shift+D).

FIXME: PNG icons?

## Suggested Workflow & Support Files
While each artist prefers his or her own way of working, here's a suggestion how to create all the needed icon versions with as little effort as possible.

Start with the vector icon, having an extra 1:1 view to precisely positioned orthogonals.
Once finished with the SVG icon, render the icon at 22×22 pixels (either as an export from your vector software or as an import in your bitmap editor) and use the results as a starting point. Most of the time, all you need to do is to recreate the outline stroke and the inner tango highlight with a 1×1 pixel brush.
The 16×16 pixel version may start from the SVG as well, but usually the shapes need to be simplified significantly. Having the 22×22 pixel version open just for precise color picking is enough. Sometimes it's also good to start with a detail of the 22×22 pixel version.
Here's a few sample videos of a Tango icon creation workflow in Inkscape and GIMP.

Alternatively, you can create the low resolution version in the vector editor as well:

Create a duplicate of the vector icon (in your vector editor).
Reduce the graphic to the target size.
Tweak the shapes, aligning the vectors (or groups of vectors) to the pixel grid.
Export and tweak if necessary.

## Things to Keep in Mind…
Here are a few things we suggest you take in consideration when transition from existing icon style…

### KDE artist
- The stroke (object outline) is 1 pixel for the 48×48 pixel target resolution. KDE icons tend to have a thicker outline.
- Only add glossiness for objects which have a shiny property in real life.

### GNOME artist
- The toolbar size of 24×24 pixels is not used in Tango themes; it's 22×22 pixels instead.
- The color palette is more vibrant, saturated.
- Every icon requires all the sizes provided.

## Frequent Mistakes
![Bad Buttonizing](Bad-buttonizing.png)

This icon does not have an easily distinguishable silhouette.
![Bad Polarizing](Bad-polarizing.png)

The overdone shiny, reflective highlight obscures the actual content.

## Contribute

Contributions are always welcome!

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, all copyright and related or neighboring rights to this work.
