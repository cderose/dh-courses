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

Keep in mind that ArcGIS Online does not have an undo option - save often by clicking the folder icon midway down the left pane.

### Adding map layers
We're going to add two map layers: one with a dataset and one with the map we georeferenced.  

#### Uploading a dataset layer
To add a CSV spreadsheet with data, click on Layers (the symbol is stacked squares) -> Add -> Add layer from file. Add the arcgis-viralTexts-beautifulSnowText.csv dataset. (If you've already added this dataset to your ArcGIS account, change the name of the file before uploading it, or ArcGIS won't let you save it.) In the data preview screen that appears, confirm that ArcGIS is interpreting the data correctly. In this case, all of the interpretations are correct, so we can click Next all the way through.  

Give your map a title, tags, and summary that are meaningful for your project. In the summary, I generally like to include where the dataset came from.

The final step is to click Create and add to map.

#### Uploading a georeferenced map layer
Click on Layers -> Add -> Add layer from URL. Paste in the base URL from Old Maps Online. Click Add custom parameter and in the first box, paste in the key parameter (without the ? or =), and in the second box, paste in the value after the equal sign. Repeat this step for the SERVICE and REQUEST parameters. Click Next and add the basemap.  

You cam toggle layers on and off in the Layers pane by clicking on the eye symbol. 

### Changing the look of the map
Ensure that the data map layer is selected in the Layers pane.

From the right Properties pane, you can experiment with the following settings to change the look of your map:  
- Styles (heat map, single symbol)
- Effects (whole layer, feature-specific - this option creates a filter)
- Aggregation (clustering)
- Pop-ups (enable and edit fields to change what appears in the pop ups)
- Show Labels (adds a label to the data points)
- Sketches (creates a new map layer where you can annotate your map to call attention to particular points)

### Publishing your ArcGIS Online Map
Click on the Share button in the left pane to either create a standalone application of your map or to export your map into a StoryMap.

## StoryMaps
StoryMaps give you the ability to combine maps, text, images, videos, and audio in an interactive website.

### Choosing a theme
Click on the Design tab to choose the theme (or look) of your StoryMap.

### Previewing your StoryMap
Click on Preview to see what your StoryMap will look like to end users. Importantly, you can adjust the preview to see what your StoryMap will look like on different devices (mobile, tablet, desktop, full screen).  

### Publishing your StoryMap
CLick on Publish to make your StoryMap publicly available.

### Building your StoryMap
Click on the plus sign button to add media to your StoryMap. When adding media, think about what you want the end user experience to be - should they scroll through your story in a linear format or can they jump around?  
