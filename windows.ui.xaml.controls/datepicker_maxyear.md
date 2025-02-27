---
-api-id: P:Windows.UI.Xaml.Controls.DatePicker.MaxYear
-api-type: winrt property
---

<!-- Property syntax
public Windows.Foundation.DateTime MaxYear { get;  set; }
-->

# Windows.UI.Xaml.Controls.DatePicker.MaxYear

## -description

Gets or sets the maximum Gregorian year available for picking.

Equivalent WinUI property: [Microsoft.UI.Xaml.Controls.DatePicker.MaxYear](/windows/winui/api/microsoft.ui.xaml.controls.datepicker.maxyear).

## -property-value

The maximum Gregorian year available for picking.

## -remarks

You can set the [MinYear](datepicker_minyear.md) and `MaxYear` properties to restrict the date values in the picker. By default, `MinYear` is set to 100 years prior to the current date and `MaxYear` is set to 100 years past the current date.

If you set only `MinYear` or `MaxYear`, you need to ensure that a valid date range is created by the date you set and the default value of the other date; otherwise, no date will be available to select in the picker. For example, setting only `yearDatePicker.MaxYear = new DateTimeOffset(new DateTime(900, 1, 1));` creates an invalid date range with the default value of `MinYear`.

The MaxYear property can't be set as a XAML attribute string, because the Windows Runtime XAML parser doesn't have a conversion logic for converting strings to dates as [DateTime](../windows.foundation/datetime.md) / [DateTimeOffset](/dotnet/api/system.datetimeoffset?view=dotnet-uwp-10.0&preserve-view=true) objects. Here are some suggested ways these objects can be defined in code and set to a date other than the current date.

+ [DateTime](../windows.foundation/datetime.md): Instantiate a [Windows.Globalization.Calendar](../windows.globalization/calendar.md) object (it is initialized to the current date). Set [Year](../windows.globalization/calendar_year.md), or call [AddYears](../windows.globalization/calendar_addyears_1853430648.md), to adjust the date. Then, call [Calendar.GetDateTime](../windows.globalization/calendar_getdatetime_624256552.md) and use the returned [DateTime](../windows.foundation/datetime.md) to set MaxYear.
+ [DateTimeOffset](/dotnet/api/system.datetimeoffset?view=dotnet-uwp-10.0&preserve-view=true): Call the  constructor. For the inner [System.DateTime](/dotnet/api/system.datetime?view=dotnet-uwp-10.0&preserve-view=true), use the  constructor signature. Or, construct a default [DateTimeOffset](/dotnet/api/system.datetimeoffset?view=dotnet-uwp-10.0&preserve-view=true) (it is initialized to the current date) and call [AddYears](/dotnet/api/system.datetimeoffset.addyears?view=dotnet-uwp-10.0&preserve-view=true).

Another possible technique is to define a date that's available as a data object or in the data context, then set MaxYear as a XAML attribute that references a [{Binding} markup extension](/windows/uwp/xaml-platform/binding-markup-extension) that can access the date as data.

## -examples

This example demonstrates setting the `MinYear` and `MaxYear` properties in code.

```xaml
<DatePicker x:Name="myDatePicker"/>
```

```csharp
public MainPage()
{
    this.InitializeComponent();
    myDatePicker.MinYear = new DateTimeOffset(new DateTime(1950, 1, 1));
    myDatePicker.MaxYear = DateTimeOffset.Now.AddYears(5);
}
```

## -see-also

[MinYear](datepicker_minyear.md), [Date picker](/windows/uwp/design/controls-and-patterns/date-picker)
