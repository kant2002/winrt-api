---
-api-id: P:Windows.UI.Xaml.Media.Imaging.SvgImageSource.RasterizePixelWidth
-api-type: winrt property
---

<!-- Property syntax.
public double RasterizePixelWidth { get;  set; }
-->

# Windows.UI.Xaml.Media.Imaging.SvgImageSource.RasterizePixelWidth

## -description
Gets or sets the width to use for SVG rasterization operations.

Equivalent WinUI property: [Microsoft.UI.Xaml.Media.Imaging.SvgImageSource.RasterizePixelWidth](/windows/winui/api/microsoft.ui.xaml.media.imaging.svgimagesource.rasterizepixelwidth).

## -xaml-syntax
```xaml
<SvgImageSource RasterizePixelWidth="double"/>
```

## -property-value
The width (in logical pixels) to use for SVG decoding operations. The default is NaN.

## -remarks
Since the units are logical pixels, the SVG is decoded using values that are pre-factored for the logical resolution, and it potentially won't use as much memory.

If [RasterizePixelHeight](svgimagesource_rasterizepixelheight.md) and RasterizePixelWidth are NaN, then the application's layout will determine the decode size so that the [SvgImageSource](svgimagesource.md) fits
in the available space.

> [!NOTE]
> In C#, you can obtain NaN from [Double.NaN](/dotnet/api/system.double.nan?view=dotnet-uwp-10.0&preserve-view=true).
>
> In C++, you can obtain NaN by using the [`NAN` macro](/cpp/standard-library/cmath) or [`std::numeric_limits<double>::quiet_NaN()`](/cpp/standard-library/numeric-limits-class#quiet_nan).
>
> Do not use the `==` operator to test for NaN.
>
> In C#, use [Double.IsNaN()](/dotnet/api/system.double.isnan?view=dotnet-uwp-10.0&preserve-view=true) to test for NaN.
>
> In C++, use [isnan()](/cpp/c-runtime-library/reference/isnan-isnan-isnanf) to test for NaN.
