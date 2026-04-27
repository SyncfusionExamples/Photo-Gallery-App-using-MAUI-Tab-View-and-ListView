# Photo-Gallery-App-using-MAUI-Tab-View-and-ListView

**Repository Description**  
This repository contains a .NET MAUI sample application that demonstrates how to build a photo gallery app using the Syncfusion MAUI TabView and ListView components.

The sample illustrates how to organize photos, albums, and favorites into separate tabs using a bottom‑placed TabView, while displaying rich, scrollable content using ListView layouts.

## Project Overview
The purpose of this project is to help developers understand how to combine the Syncfusion MAUI TabView and ListView controls to build a modern, feature‑rich photo gallery application in .NET MAUI. It demonstrates tab‑based navigation, icon customization, grid layouts, and responsive data presentation.

## Features
- Integration of Syncfusion MAUI TabView component  
- Bottom TabBar placement with customizable icons  
- Photo, Album, and Favorites tabs  
- Grid‑based image layout using ListView  
- Font‑based icon customization using `FontImageSource`  
- Dynamic data binding and item tap handling  

## Prerequisites
Ensure the following requirements are met before running the project:
- Visual Studio with **.NET MAUI workload** installed  
- Supported platform SDKs (Android, iOS, Windows, or MacCatalyst)

## Installation and Running the Application
1. Clone this repository to your local machine.
2. Open the solution file in Visual Studio.
3. Restore NuGet packages if prompted.
4. Select the target platform (Android, iOS, Windows, or MacCatalyst).
5. Build and run the project to view the Photo Gallery application.

## Sample Layout
This project includes a XAML‑based UI implementation that demonstrates:
- Tab header customization using `SfTabItem`
- Icon color binding through the selected tab state
- Grid layouts for images using `SfListView` and `GridLayout`
- Responsive image presentation in multiple tab views  
```xaml
    <Grid>
        <tabView:SfTabView EnableRippleAnimation="False" TabBarPlacement="Bottom" EnableSwiping="True" IndicatorStrokeThickness="0"  TabBarHeight="55">
            <tabView:SfTabItem Header="Photos" x:Name="photosTab" ImageTextSpacing="5">
                <tabView:SfTabItem.ImageSource>
                    <FontImageSource Glyph="&#xE703;" FontFamily="PhotoGallery"
                                     Color="{Binding Source={x:Reference photosTab},Path=TextColor}"/>
                </tabView:SfTabItem.ImageSource>
                <listView:SfListView x:Name="listViewPhotos" ItemsSource="{Binding Photos}" SelectionMode="None"
                                     ItemSize="90" ItemSpacing="5" ItemTapped="OnPhotosItemTapped">
                    <listView:SfListView.ItemsLayout>
                        <listView:GridLayout SpanCount="4"/>
                    </listView:SfListView.ItemsLayout>
                    <listView:SfListView.ItemTemplate>
                        <DataTemplate>
                            <Image Source="{Binding Image}" Aspect="AspectFill" HeightRequest="88" WidthRequest="88"/>
                        </DataTemplate>
                    </listView:SfListView.ItemTemplate>
                </listView:SfListView>
            </tabView:SfTabItem>

            <tabView:SfTabItem Header="Albums" x:Name="albumsTab" ImageTextSpacing="5">
                <tabView:SfTabItem.ImageSource>
                    <FontImageSource Glyph="&#xE704;" FontFamily="PhotoGallery"
                                     Color="{Binding Source={x:Reference albumsTab},Path=TextColor}"/>
                </tabView:SfTabItem.ImageSource>

                <listView:SfListView ItemsSource="{Binding Albums}" ItemSize="230"
                             ItemTapped="OnAlbumsItemTapped" SelectionMode="None">
                    <listView:SfListView.ItemsLayout>
                        <listView:GridLayout SpanCount="2" />
                    </listView:SfListView.ItemsLayout>
                    <listView:SfListView.ItemTemplate>
                        <DataTemplate>
                            <Grid RowDefinitions="*,20,20">
                                <Image Source="{Binding CoverImage}" Aspect="Fill" HeightRequest="180" WidthRequest="180"/>
                                <Label Text="{Binding AlbumName}" FontSize="15" Margin="10,0,0,0" Grid.Row="1"/>
                                <Label Text="{Binding Count, StringFormat='{0} items'}" Margin="10,0,0,0" FontSize="12" Grid.Row="2" />
                            </Grid>
                        </DataTemplate>
                    </listView:SfListView.ItemTemplate>
                </listView:SfListView>
            </tabView:SfTabItem>

            <tabView:SfTabItem Header="Favorites" x:Name="favoritesTab" ImageTextSpacing="5">
                <tabView:SfTabItem.ImageSource>
                    <FontImageSource Glyph="&#xE705;" FontFamily="PhotoGallery"
                                     Color="{Binding Source={x:Reference favoritesTab},Path=TextColor}"/>
                </tabView:SfTabItem.ImageSource>
                <listView:SfListView x:Name="listViewFavorites" ItemsSource="{Binding Favorites, Mode=TwoWay}" ItemSpacing="10"
                                     SelectionMode="None" AutoFitMode="Height" ItemTapped="OnPhotosItemTapped">
                    <listView:SfListView.ItemTemplate>
                        <DataTemplate>
                            <Grid RowDefinitions="30,*">
                                <Label Text="{Binding DateTime, StringFormat='{0:ddd, dd MMM, yyyy}'}" 
                                       FontAttributes="Bold" FontSize="15" />
                                <Image Source="{Binding Image}" Aspect="AspectFill" Grid.Row="1"/>
                            </Grid>
                        </DataTemplate>
                    </listView:SfListView.ItemTemplate>
                </listView:SfListView>
            </tabView:SfTabItem>
        </tabView:SfTabView>
    </Grid>
```

## Usage
Run the application and interact with the following tabs:
- **Photos:** Displays images in a grid layout  
- **Albums:** Shows album cards with cover images and item counts  
- **Favorites:** Displays favorite photos grouped by date  

You can modify the data bindings and layouts in XAML to customize the gallery behavior.

## Documentation
- **General Syncfusion documentation:**  
  https://help.syncfusion.com/
- **.NET MAUI Introduction:**  
  https://help.syncfusion.com/maui/introduction/overview

## Additional Resources
- **System requirements for .NET MAUI:**  
  https://help.syncfusion.com/maui/system-requirements

## Troubleshooting

### Path Too Long Exception
If you encounter a *path too long* error when building the project:
1. Close Visual Studio.
2. Rename the repository folder to a shorter name.
3. Reopen the solution and rebuild the project.

## License
Syncfusion has no liability for any damage or consequence that may arise from using or viewing the samples. The samples are for demonstrative purposes only. By accessing or using these samples, you acknowledge that Syncfusion shall not be held responsible for any damages resulting from their use.