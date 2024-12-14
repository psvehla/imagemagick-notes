# ImageMagick Notes

Stuff I've figured out how to do with ImageMagick that wasn't a quick lookup.

## Modify an Image to a Specific Size

I had a digital passport photo, but needed it to be 4x6cm for a visa application for Laos. The photo was too big (40x50cm) and at 75dpi. Resize made it too grainy, what I needed to do was increase the pixel density.

```bash
convert passport.jpg -units PixelsPerCentimeter -density 226 pex.jpg
```

The aspect ratio of the photo wasn't quite right so I got the height of the photo to 6cm, then cropped the sides to 4cm.

```bash
convert pex.jpg -gravity Center -crop 905x1358+5+0 pex2.jpg
```
