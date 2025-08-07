# Mapping tutorial

## Old Maps Online
[Website](https://www.oldmapsonline.org/en#position=3/42.39/-71.1)

### Upload a map
- Click on “My maps” and then click "Add a new map"
- Click "upload an image"
  After the image loads, you might see a 403 Not Authorized warning. Ignore it and click "Go back", followed by "My maps" again.
- Click on the loaded map and select “Metadata”.
- Provide metadata information, accept the site terms, and then check the “Add as a private map” box.
  The Georeferencer view should open automatically. (If it doesn’t, click on “My maps” and select “Georeferencer” underneath the map image.)

### Georeference the map
- From the left map, click the “Globe” icon and select a simple basemap.
- Beginning with the map on the left, click on a spot and then select the corresponding spot on the right to drop pins that link the locations.
- Continue adding pins. Place them across the map — you want a balance of close and distant points. Keep an eye out for recognizable features.
- For quality checks along the way, click “Overlay” and toggle the transparency slider.
- At some point, the tool will start guessing where the matching pin should go. Adjust the suggested location as needed.
- When you’re finished, click “Save”.

## ArcGIS Online
[Website](https://www.arcgis.com/home/index.html)  

Note: If you ever don’t see all appearance options on the right side, make sure you have the correct map layer selected.

### Load data
- Drag CSV over map

### Change basemap
- From left column, click "Basemap"  
- Select newspaper map

### Add another map layer
- From left column, click "Layers" then click "Add"
- Change the dropdown from "My Content" to "ArcGIS Online"
- Search for “Nineteenth century United States”
- Select “Railroads 1826-1911”

#### Adjust Railroad layer's properties
- From right column, click "Properties"
- Change transparency to 58%
- From right column, click "Styles"
- Select location single style and change the color

### Adjust ViralText layer's properties
- From left-column, click "Layers" and then click the virtalTexts layer
- From right column, click "Styles"
- Try a heat map
- Click location single symbol -> Style options
- Click the pencil icon to edit the symbol
- Click “basic point”
- Click the category dropbox to select a different shape
- Choose firefly (or another symbol of interest)
- Change point size to 20

#### Add effects
- From right column, click "Effects"
- Turn on bloom
- Add drop shadow

#### Cluster points
- From right column, click "Aggregation"
- Enable aggregation

#### Save map
- From left column, click "Save and open" -> and then click "Save"

#### Add labels
- From right column, click "Labels"
- Change label field to “publication”
- Add label color 3b3a3a
- Show filters option
- Disable labels

#### Add pop-up
- From right column, click "Pop-ups"
- Provide a title
- Provide a Fields list title and description
- Remove latitude and longitude information by clicking the "X"

#### Explore options for sharing the map
- From the left column, click "Share map"
- From left column, click three dots and select "Create app"
- From left column, click three dots and select "Create print"

Save your map.

## StoryMaps
[Website](https://storymaps.arcgis.com/stories)  

- Click the + sign to add content.  
If you have a subscription, you can use the embed feature, which would let you bring in your interactive Tableau Public visualizations (you can include the static versions as images for free)

The top tabs work as follows:
- Design gives organizational options
- Insights flags issues
- Preview lets you see what the project looks like for different media sizes
- Publish lets you save your story
- Click the three dots to see additional settings (such as for language and permissions)
