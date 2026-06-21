# Images

> Delivering artwork at the right format and resolution so it looks sharp on every display.

**Use it for:** Whenever you ship raster or vector imagery, photos, or illustrations across varied screen densities.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<img srcset>`/`sizes`, `<picture>`, WebP/AVIF, SVG, `loading="lazy"`, color-managed assets |
| SwiftUI | Asset catalog with 1x/2x/3x, `Image`, `.resizable()`/`.aspectRatio()`, vector PDF assets, `AsyncImage` |
| Android (Compose) | Density buckets (mdpi…xxxhdpi) or vector drawables, `Image`/`painterResource`, `Coil` for remote |
| React Native | `require()` with `@2x`/`@3x` suffixes, `Image`/`FastImage`, `resizeMode` |
| Flutter | Resolution-aware assets (`2.0x`/`3.0x`), `Image.asset`/`Image.network`, `BoxFit`, SVG via `flutter_svg` |

**Guidelines**
- Serve high-resolution assets for high-density displays (1x/2x/3x or width descriptors), not one fixed bitmap.
- Use the right format: vector for flat icons/art that scales; JPEG/WebP/AVIF for photos; PNG for transparency.
- Prefer modern formats with fallbacks for smaller files at equal quality.
- Align art to a whole-pixel grid at 1x so it stays crisp at 2x/3x.
- Embed/attach a color profile (sRGB) for consistent rendering.
- Optimize and compress; lazy-load offscreen images.
- Test on real devices and varied sizes — previews can hide pixelation or stretching.

**Accessibility**
- Provide meaningful alt text / `contentDescription` / `semanticLabel`; mark decorative images empty/hidden.
- Don't bake essential information only into an image without a text equivalent.
- Ensure text rendered in images meets contrast (prefer real text over text-in-image).

**Avoid**
- Shipping a single low-res bitmap that blurs on high-density screens.
- Using raster formats for art that must scale.
- Unoptimized, oversized image files.

**Full reference:** [Apple HIG](../../references/foundations/images.md)
