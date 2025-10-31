# Photo-Gallery-App-using-MAUI-Tab-View-and-ListView

This sample shows how to build a photo gallery app using .NET MAUI TabView and ListView controls in your .NET MAUI application.

## Sample

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

## Requirements to run the demo

To run the demo, refer to [System Requirements for .NET MAUI](https://help.syncfusion.com/maui/system-requirements)

## Troubleshooting:

### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

## License

Syncfusion has no liability for any damage or consequence that may arise from using or viewing the samples. The samples are for demonstrative purposes. If you choose to use or access the samples, you agree to not hold Syncfusion liable, in any form, for any damage related to use, for accessing, or viewing the samples. By accessing, viewing, or seeing the samples, you acknowledge and agree Syncfusion's samples will not allow you seek injunctive relief in any form for any claim related to the sample. If you do not agree to this, do not view, access, utilize, or otherwise do anything with Syncfusion's samples
