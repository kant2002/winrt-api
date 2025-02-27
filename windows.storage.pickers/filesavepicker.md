---
-api-id: T:Windows.Storage.Pickers.FileSavePicker
-api-type: winrt class
---

<!-- Class syntax.
public class FileSavePicker : Windows.Storage.Pickers.IFileSavePicker, Windows.Storage.Pickers.IFileSavePicker2, Windows.Storage.Pickers.IFileSavePicker3
-->

# Windows.Storage.Pickers.FileSavePicker

## -description

Represents a file picker that lets the user choose the file name, extension, and storage location for a file.

In a desktop app, before using an instance of this class in a way that displays UI, you'll need to associate the object with its owner's window handle. For more info, and code examples, see [Display WinRT UI objects that depend on CoreWindow](/windows/apps/develop/ui-input/display-ui-objects#winui-3-with-c).

## -remarks

> [!IMPORTANT]
> You must use the [FileTypeChoices property](filesavepicker_filetypechoices.md) property to specify one or more file types before you call the PickSaveFileAsync method, or the picker will thrown an exception. 

To learn how to save files through the file picker, see [How to save files through file pickers](/windows/uwp/files/quickstart-save-a-file-with-a-picker).

To get started accessing files and folders file picker, see [Files, folders, and libraries ](/windows/uwp/files/index).

> [!WARNING]
> If you try to show the file picker while your app is snapped the file picker will not be shown and an exception will be thrown. You can avoid this by making sure your app is not snapped or by unsnapping it before you call the file picker. The following code examples and the [File picker sample](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples/FilePicker) show you how.

### Version history

| Windows version | SDK version | Value added |
| -- | -- | -- |
| 1903 | 18362 | CreateForUser |
| 1903 | 18362 | User |

## -examples

The [File picker sample](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples/FilePicker) is available in C# and C++/WinRT versions. It demonstrates how to check whether the app is snapped, how to set file picker properties, and how to show a file picker so that the user can save a file.

Here's an excerpt from the C# version of the samle app.

[!code-csharp[all_savepicker_checksnapped_show](../windows.storage.pickers/code/FilePicker/CS/Scenario4.xaml.cs#Snippetall_savepicker_checksnapped_show)]

## -see-also

[File picker sample (Windows 10)](https://github.com/Microsoft/Windows-universal-samples/tree/master/Samples/FilePicker), [Files, folders, and libraries](/windows/uwp/files/index), [How to save files with a file picker](/windows/uwp/files/quickstart-save-a-file-with-a-picker),  [Windows.Storage.StorageFile class](../windows.storage/storagefile.md), [Display WinRT UI objects that depend on CoreWindow](/windows/apps/develop/ui-input/display-ui-objects)
