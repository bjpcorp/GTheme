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

1. Object Outline:
All Gramps icons are stroked with a thin outline to improve contrast. At low resolutions the stroke size is 1px. The stroke should not scale along with the icon, it should remain 1px.
The color of the outline is a dark variant of the key color of the icon. This is done by retaining the hue and saturation of the dominant fill color and lowering the value to approximately 20%). In the example above, the trashcan is green, so the stroke will be green as well.

2. Highlights:
The edges of objects tend to reflect light more due to the fact the position of the observer relative to the light source is almost always ideal for the reflection. In terms of highlights, the theme inherits the style of Tango, Firefox/Thunderbird, Pinstripe/Winstripe designed by Kevin Gerich & Stephen Horlander (Pinstripe, Winstripe) which shift away from reality by creating a second inner outline of the object. This stroke is very subtle and may not be apparent on some matte objects.

3. Glossy Reflections:
Use glossy reflection only on objects that have a reflective surface in real life (plastic, glass, some metal, et cetera). A sheet of paper certainly doesn't have such attribute.
Various elements have been picked from existing icon styles: Similar perspective as GNOME icons, a colored object stroke from KDE, an Aqua-like highlight influenced by Mac OS X, and edge highlights and overall lightness from the Firefox Pinstripe theme.

## Style Attributes

- [Amazing GitHub Template](https://github.com/dec0dOS/amazing-github-template#readme) - Useful README.md, LICENSE, CONTRIBUTING.md, CODE_OF_CONDUCT.md, SECURITY.md, GitHub Issues, Pull Requests and Actions templates to jumpstart your projects.
- [Common Readme](https://github.com/noffle/common-readme#readme) - A common readme style for Node. Includes a guide and a readme generator.


## Perspective

- [Gifox](https://gifox.io) - **$14.99** - Cleanest UI, hotkeys, lots of advanced features
- [Gifski](https://github.com/sindresorhus/Gifski#readme) - **FREE** - More vivid colors than the rest, but still keep size low


## Lighting

- [feedmereadmes](https://github.com/LappleApple/feedmereadmes#readme) - Free README editing+feedback to make your open-source projects grow. See the README maturity model to help you keep going.
- [maintainer.io](https://maintainer.io/) - Free README standardization and feedback, if you click on 'Book an audit'.

## Sizes
- Large
- Medium
- Small

## Common Filenaming

## Metainformation

## Suggested Workflow & Support Files

## Things to Keep in Mind…

## Frequent Mistakes

## Contribute

Contributions are always welcome!
Please read the [contribution guidelines](contributing.md) first.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Matias Singers](https://mts.io) has waived all copyright and related or neighboring rights to this work.
