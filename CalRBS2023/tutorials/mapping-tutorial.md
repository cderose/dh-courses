# Mapping tutorial

## Old Maps Online Georeferencer

### Georeferencing maps
[Old Maps Online](https://www.oldmapsonline.org/partners/georeferencer/) is one resource you can use for georeferencing a map (or really, any image). The limitation is that you can only georeference one map for free.  

To get started, sign in and click on My Maps. From there, you can upload an image of the map that you want to georeference.  

After it uploads, you'll be taken to the screen where you can place pins (or points) for establishing points of connection between the two maps. (If that page didn't redirect there by default, click on My Maps and then Georeference.  

In general, you want to place between six to ten pins, far apart from one another.  To place a pin, click on one of the maps and then click one the corresponding spot in the other map.  

You'll see the georeferencer software start to make predictions after you've placed a few pins. It might also try to rotate the image.  

Click Overlay at any point to see how the map is doing. From Overlay, you can adjust a slider to set the transparency of the overlaid map.  

When you're happy, click Save.

### Viewing the georeferenced map
To interact with your georeferenced map, click on My Maps and go to Compare. This view gives you the ability to look at your map as a Grid (side by side), Swipe (an overlay), and Spy Glass (the georeferenced map appears in the spy glass).   

To share your georeferenced map, click on the share button symbol next to My Maps.  That link is publicly shareable (peoople don't need an Old Maps Online account to see it.)  

### Retrieving the Web Map Tile Service URL for ArcGIS Online
To retrieve the URL that you can use to upload your georeferenced map into ArcGIS Online, click on My Maps and go to This Map. Copy the link under Web Map Tile Service (WMTS).  

The full URL will resemble the following: https://maps.georeferencer.com/georeferences/9c700e94-47d2-49cf-ac14-77b769f08999/2023-08-03T23:20:47.570150Z/wmts?key=aVEqvrwv9xBfY9mpIjnU&SERVICE=WMTS&REQUEST=GetCapabilities  

You want to save this link in a text file in the following pieces for ArcGIS Online:  
- https://maps.georeferencer.com/georeferences/9c700e94-47d2-49cf-ac14-77b769f08999/2023-08-03T23:20:47.570150Z/wmts
- ?key=aVEqvrwv9xBfY9mpIjnU
- &SERVICE=WMTS
- &REQUEST=GetCapabilities

The key-value pairs after the ? and & represent parameters in your URL. When we upload our georeferenced map to ArcGIS Online, we need to specify the parameters separately from the base URL.  

## ArcGIS Online
After you log in to [ArcGIS Online](https://www.arcgis.com/home/index.html), click on Map to create a new map project.  

### Adding map layers
We're going to add two map layers: one with a dataset and one with the map we georeferenced.  

### Uploading a dataset
To add a CSV spreadsheet with data, click on Layers (the symbol is stacked squares) -> Add -> Add layer from file. Add the arcgis-viralTexts-beautifulSnowText.csv dataset. (If you've already added this dataset to your ArcGIS account, change the name of the file before uploading it, or ArcGIS won't let you save it.) In the data preview screen that appears, confirm that ArcGIS is interpreting the data correctly. In this case, all of the interpretations are correct, so we can click Next all the way through.  

Give your map a title, tags, and summary that are meaningful for your project. In the summary, I generally like to include where the dataset came from.

The final step is to click Create and add to map.

### Uploading a georeferenced map

## StoryMaps
