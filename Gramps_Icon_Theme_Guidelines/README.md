# Gramps Icon Theme Guidelines
1. [Introduction](#Introduction)	
2. [Colour Palette](#Colour-Palette)	
3. [Defining Gramps Style Elements](#defining-gramps-style-elements) 
   1. [Object Outline](#1-object-outline)
   2. [Highlights](#2-highlights)
   3. [Glossy Reflections](#3-glossy-reflections)
4. [Style Attributes](#style-attributes)
5. [Perspective](#perspective)
   1. [Flat On The-Shelf Perspective](#1-flaton-the-shelf-perspective)
   2. [On The Table](#2-on-the-table)
   3. [Tilted Table](#3-tilted-table)
6. [Lighting](#lighting)
7. [Sizes](#sizes)
   1. [Extra Small 16x16px](#--x-small)
   2. [Small 22x22px](#--small)
   3. [Medium 32x32px](#--medium)
   4. [Large 48x48px](#--large)
   5. [Extra Large 256x256px](#--x-large)
8. [Common Filenaming](#common-filenaming)
9. [Metainformation](#metainformation)
10. [Suggested Workflow Support Files](#suggested-workflow--support-files)
11. [Things To Keep In Mind](#things-to-keep-in-mind)
12. [Frequent Mistakes](#frequent-mistakes)

## Introduction
The Gramps icon theme's goal is to create a distinctive theme guide for Gramps icons. A user running a multiplatform application should not have the impression that the look is unpolished and incosistent with what he or she is used to. While this isn't about merging styles of all desktop systems, we do aim to not be drastically different on each platform.

Along with a generic type fallback, having a similar style will help in the transition phase with some legacy icons which may still remain on a user's particular desktop.

## Colour Palette
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

![Icon Elements](Unify-icon-elements.png)


### 1. Object Outline
All Gramps icons are stroked with a thin outline to improve contrast. At low resolutions the stroke size is 1px. The stroke should not scale along with the icon, it should remain 1px.
The color of the outline is a dark variant of the key color of the icon. This is done by retaining the hue and saturation of the dominant fill color and lowering the value to approximately 20%). In the example above, the trashcan is green, so the stroke will be green as well.

### 2. Highlights
The edges of objects tend to reflect light more due to the fact the position of the observer relative to the light source is almost always ideal for the reflection. In terms of highlights, the Gramps theme inherits the style of Tango, Firefox/Thunderbird, Pinstripe/Winstripe designed by Kevin Gerich & Stephen Horlander (Pinstripe, Winstripe) which shift away from reality by creating a second inner outline of the object. This stroke is very subtle and may not be apparent on some matte objects.

### 3. Glossy Reflections
Use glossy reflection only on objects that have a reflective surface in real life (plastic, glass, some metal, et cetera). A sheet of paper certainly doesn't have such attribute.
Various elements have been picked from existing icon styles: Similar perspective as GNOME icons, a colored object stroke from KDE, an Aqua-like highlight influenced by Mac OS X, and edge highlights and overall lightness from the Firefox Pinstripe theme.

## Style Attributes
To better understand the style of Gramps, consider the following adjectives:

- Light
- Crisp
- Straight
- Simplified
- Modern
- Well-balanced

## Perspective

There are three types of perspective defined for Gramps:

### 1. Flat/On the Shelf Perspective

![Flat On The Shelf Perspective](On-the-shelf-perspective.png)

This style resembles looking at an object on a shelf at eye level, looking at an object from above, or laying on surface. This is the most common perspective for toolbar icons and document mime type icons.

### 2. Tilted Table

![Tilted Table Perspective](tilted-table-perspective.png)

In cases where the object's appearance is more evident from an angle, you are free to use the tilted table perspective???but this is the least common perspective of the three and should be used only in cases where the other two do not provide a clearly distinctive silhouette of the object.

### 3. On the Table

![On The Table Perspective](Table-perspective.png)

This type of perspective is the most common for application icons. Action/Toolbar icons also utilize this perspective from time to time.

## Lighting

![Lighting](100px-Lighting.png)

Having homogenous lighting across all icons also is important for visual consistency. Gramps icons are lit from above, with the light source slightly to the left. Icons with on the table perspective may cast a fuzzy shadow on the surface as if the light source came from the position of the observer.

## Sizes
There are 4 major icon sizes defined that an icon theme should contain: Large, Medium, Small and Extra Small. Each of these sizes needs to be treated separately, simple scaling of a larger icon doesn't work and ends up looking fuzzy and unclear. On top of that, a new optional size, X-Large, has been introduced.

### - X-Small
![X-Small Folder](x-directory-normal-drag-accept3.png)

At 16??16 pixels, the "Extra Small" size is used in places such as lists (file dialog, message list in an e-mail client, etc.) and menus.

### - Small
![Small Folder](x-directory-normal-drag-accept2.png)

Its bitmap size is 22??22 pixels. "Small" is the common size for application toolbar icons in KDE and the GIMP
Gnome has been using a size of 24??24px (which is ?? of 48??48); just adding a 1 pixel empty space on all sides can make Gramps icons useful on the Gnome desktop.

One can easily do this with imagemagick:
```convert -bordercolor Transparent -border 1x1 gramps_size.png gnome_size.png```

### - Medium
![Medium Folder](x-directory-normal-drag-accept1.png)

A very common size of 32x32 pixels is used on some menus (slab) and very common on Windows.

### - Large
![Large Folder](x-directory-normal-drag-accept.png)

The bitmap size is 48??48 pixels. This size is mainly used for desktop icons and in the file manager views.

### - X-Large
![X-Large Folder](x-directory-normal-drag-accept4.png)

This size has been introduced fairly recently and is optional.

Unless you are an experienced icon designer, do not start with this size as it goes against most of the good practice for icon design. You will be required to add insane amounts of detail and might end up with an unclear and complex metaphor.

The canvas size is 256x256px and unlike all the other sizes, this artwork can be scaled from 49px up. In other words -- do not aim for pixel perfection here.

This size also holds another exception to the rule of stroking. Do not stroke x-large icons with the 1px common everywhere. In Inkscape we use a trick that achieves a similar contrast enhancing effect without losing upwards scalability.
You create an outline object with no fill and a stroke of 3px. Then you duplicate such object and use the copy to clip itself. After blurring the object, the inside of the silhouette gets nicely shaded, while the outside is crisp. Instead of the inner stroke, use path shapes. Blur is a useful tool here as well.

## Common Filenaming
Until now, there has not been a standard for naming conventions. This resulted in themes which have not worked globally, as individual projects have used different names for the same icon.

Gramps solves this issue with a Standard Icon Naming Specification

In the short term, existing KDE and GNOME icons names will be addressed using symlinks. We have prepared a script which automatically generates appropriate symlinks for existing naming schemes in GNOME and KDE so that compatibility with current desktop applications will be preserved.

## Metainformation
To make it easier for developers to search for icons in the Gramps set, please provide keywords in the icon file. For example, appropriate keywords for a joystick icon are: controller, joystick, game, gaming, HID.

For SVG icons, the metainformation is written using the Dublin Core namespace.

Inkscape users can conveniently enter the data in the document properties (Ctrl+Shift+D).

## Suggested Workflow & Support Files
While each artist prefers his or her own way of working, here's a suggestion how to create all the needed icon versions with as little effort as possible.

Start with the vector icon, having an extra 1:1 view to precisely positioned orthogonals.

Once finished with the SVG icon, render the icon at 22??22 pixels (either as an export from your vector software or as an import in your bitmap editor) and use the results as a starting point. Most of the time, all you need to do is to recreate the outline stroke and the inner Gramps highlight with a 1??1 pixel brush.

The 16??16 pixel version may start from the SVG as well, but usually the shapes need to be simplified significantly. Having the 22??22 pixel version open just for precise color picking is enough. Sometimes it's also good to start with a detail of the 22??22 pixel version.

Here's a few sample videos of a Tango icon creation workflow in Inkscape and GIMP.

[![Creating Vector Icons with Inkscape](https://img.youtube.com/vi/NRVUWRnH5FM/mqdefault.jpg)](https://www.youtube.com/watch?v=NRVUWRnH5FM) [![Tango Bitmaps with GIMP](https://img.youtube.com/vi/ooPfYctUfgU/mqdefault.jpg)](https://www.youtube.com/watch?v=ooPfYctUfgU)

Alternatively, you can create the low resolution version in the vector editor as well:

Create a duplicate of the vector icon (in your vector editor).
Reduce the graphic to the target size.
Tweak the shapes, aligning the vectors (or groups of vectors) to the pixel grid.
Export and tweak if necessary.

## Things to Keep in Mind???
Here are a few things we suggest you take in consideration when transition from existing icon style???

### KDE artist
- The stroke (object outline) is 1 pixel for the 48??48 pixel target resolution. KDE icons tend to have a thicker outline.
- Only add glossiness for objects which have a shiny property in real life.

### GNOME artist
- The toolbar size of 24??24 pixels is not used in Gramps themes; it's 22??22 pixels instead.
- The color palette is more vibrant, saturated.
- Every icon requires all the sizes provided.

## Frequent Mistakes
![Bad Buttonizing](180px-Bad-buttonizing.png)

This icon does not have an easily distinguishable silhouette.

![Bad Polarizing](180px-Bad-polarizing.png)

The overdone shiny, reflective highlight obscures the actual content.

## Contribute

Contributions are always welcome!

## Acknowledgements
Thanks to some of the original authors and designers of the Tango Desktop Project, in alphabetical order by surname: Lapo Calamandrei, Ryan Collier, Rodney Dawes, Steven Garrity, Tuomas Kuosmanen, Garrett LeSage, Andreas Nilsson, Ulisse Perusin, Jakub Steiner, Corey Woodworth.

https://commons.wikimedia.org/wiki/Category:Tango_project

http://tango.freedesktop.org/Tango_Icon_Theme_Guidelines

## License

[![License: CC BY-SA 2.0](https://img.shields.io/badge/License-CC_BY--SA_2.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/2.0/)
