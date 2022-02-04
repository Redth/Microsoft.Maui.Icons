# Microsoft.Maui.Icons

Simple project to extract glyphs from icon fonts and generate consts for their names and unicode values

## Usage in a .NET MAUI App

You can register your fonts in the `ConfigureFonts` method like below:

```csharp
namespace MauiApp18;

public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont(Microsoft.Maui.Icons.Fluent.Regular.Filename, "FluentRegular");
				fonts.AddFont(Microsoft.Maui.Icons.Fluent.Filled.Filename, "FluentFilled");
			});

		return builder.Build();
	}
}
```

Using the font glyph:

```xml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:fluent="clr-namespace:Microsoft.Maui.Icons.Fluent;assembly=Microsoft.Maui.Icons.Fluent"
             x:Class="MyApp.MainPage">
	<Grid>
		<Image WidthRequest="40" HeightRequest="40">
			<Image.Source>
				<FontImageSource
					FontFamily="FluentRegular"
					Glyph="{x:Static fluent:Regular.checkmark_20_regular}"
					Color="Green" />
			</Image.Source>
		</Image>
	</Grid>
</ContentPage>
```
