# Introduction to Data Visualization with Tableau Public

## Overview
[Tableau Public](https://public.tableau.com/en-us/s/) is free visualization software for creating interactive data visualizations online. With a single click, you can move between different chart types to see which works better for the data and questions at hand.   

While Tableau runs locally, it saves publicly, meaning your data becomes public. For data with privacy restrictions, you should use Tableau Desktop, which saves to your local machine. [Students](https://www.tableau.com/academic/students?utm_campaign_id=2019176&utm_campaign=Prospecting-PROD-ALL-ALL-ALL-ALL&utm_medium=Paid+Search&utm_source=Google+Search&utm_language=EN&utm_country=USCA&kw=tableau%20for%20students&adgroup=CTX-Brand-Student-E&adused=RSA&matchtype=e&placement=&gclid=EAIaIQobChMI4uyd9faW6gIVkYbACh2MZgwNEAAYASAAEgIG6PD_BwE&gclsrc=aw.ds) and [educators](https://www.tableau.com/academic/teaching?utm_campaign_id=2019176&utm_campaign=Prospecting-CORE-ALL-ALL-ALL-ALL&utm_medium=Paid+Search&utm_source=Google+Search&utm_language=EN&utm_country=USCA&kw=%2Btableau%20for%20%2Bteachers&adgroup=CTX-Brand-Teaching-B&adused=ETA&matchtype=b&placement=&gclid=EAIaIQobChMIp5Spi_eW6gIVycDACh2PAQkjEAAYASAAEgLwKvD_BwE&gclsrc=aw.ds) can sign up for free yearly licenses to Tableau Desktop.

### Set Up
1. [Download, install, and then open Tableau Public](https://public.tableau.com/en-us/s/).
2. Under "Connect" in the left-hand column, click on "Text file" and select the [tableau-goodreads](https://drive.google.com/drive/folders/1hhkpAqz1hyyxmYLPe9K7VOR5e46DrfNZ?usp=sharing) CSV file. Tableau will load a preview of the dataset, giving us insight into how it is interpreting our data.
3. Review Tableau's interpretation. The symbol at the top of the header represents what data type it thinks each column contains:
- Abc = string (text) data,
- Globe = geospatial data, 
- Calendar = temporal data, 
- Hash symbol = numeric data, 
- T|F = Boolean (true or false) data. 
 
For our dataset, we need to change:
- "Birthplace" to geospatial data. To do so, click on the Abc symbol and select "Geographic Role" -> "Country/Region." The symbol for the column should have changed from Abc to a Globe now.
- "Pub Date" to a date. Click on the Abc and select "Date." The symbol should now be a calendar. You should also notice that all of our years now also have a month and day prefixed to them; by default, Tableau treats dates as month-day-year, so it adds a generic 1/1/ to the beginning of our years (it won't affect our results).
- "Book Id" to a string. Click on the hash symbol and select "String." The symbol should now be Abc.

4. To begin working with our data, click on the orange "Sheet 1" rectangle toward the bottom left-hand corner of the application. This will create our first Tableau worksheet, a blank space for generating visualizations.

![Button for New Worksheet](https://github.com/cderose/course-prep/blob/main/tableau-desktop.png)

### Bar Chart: Authors 
To start getting a sense for what our dataset looks like, let's see how many authors are represented. We can do that with a bar chart.

*To undo a step at any point, click the left arrow in Tableau. To see other visualization types that are available once you start selecting items from the Tables section, click on the "Show Me" button.*

1. Double click on the "tableau-goodreads.csv" pill (this is a generated column that Tableau created that sums all of the records in our spreadsheet) and double click on "Author Name."
2. Swap the axes by clicking on the upside down "L" icon in the top toolbar.
3. To sort from least to greatest or greatest to least, click on the ascending or descending stacked rectangles icons.
4. To see the breakdown of authors by gender click on the "Author Gender" pill and drag it over the "Color" Marks card. To change the colors being used, click the dropdown for the "Author Gender" legend (you might have to click off "Show Me" to see it) -> "Edit Colors." I tend to use the colors in the "Color Blind" palette to help ensure my color choices will be widely accessible.
5. To color the rows by genre instead (which will show us what genre(s) each author wrote in), drag the "Genre" pill over "Color." We will get a warning since we have over 100 genres and good practice is to use the color channel for 10 or fewer categories, but since we're creating an exploratory visualization just for ourselves to get a handle of the dataset, click "Add all members" and proceed.
6. Update the x-axis label to something clearer by clicking on the current label, "Count of tableau-goodreads.csv." In the pop-up that appears, type "Number of Books" for the new label. Click the "X" when finished. 
7. Give the chart a meaningful title by double clicking on the current title, "Sheet 1." Remove "\<Sheet Name>" and type a new title based on the settings you have in place. 
8. For the last step, give a title to this sheet in Tableau. Double click on "Sheet 1" in the bottom bar and rename it "bar chart of authors."

### Bar Chart: Genres
Let's take a closer look at the breakdown of genres in our dataset with a new bar chart.

1. Click on the new sheet icon to open a new, blank workspace.
2. Double click on the "tableau-goodreads.csv" pill and "Genre."
3. Swap axes and sort from greatest to least (see the first bar chart for the steps if you need a refresher).
4. Drag "Author Gender" over "Color" to see the breakdown for each genre.
5. To make the breakdown clearer, drag "tableau-goodreads.csv" over the "Label" Marks card. Now we can see the exact number of authors writing for each genre based on our dataset.
6. To turn the number into a percentage, click the dropdown for the green "CNT(tableau-goodreads.csv)" pill in our Marks card area -> "Quick Table Calculation" -> "Percent of Total." By default, Tableau is showing us the aggregate percentage for the entire dataset. To be able to ask questions such as, "what genres are mostly written by women versus men in this dataset?", we need to change how Tableau is doing the calculation. Click on the dropdown for "CNT(tableau-goodreads.csv)" again -> "Compute using" -> "Table (across)." Now we can see that the mystery genre is 50%-50% when it comes to men and women authors, versus more women writing young adult novels and more men writing science fiction (in this dataset, anyway).
7. Practice adding a graph title, a clearer x-axis label, and a title for the worksheet. See the first bar chart we made if you need the steps.

### Line Graph: Genres Published over Time
1. Click on the new sheet icon to open a new, blank workspace.
2. Double click on the "tableau-goodreads.csv" pill and "Pub Date." We can see that we have a long tail of years where only one book was published.
3. For a closer view of the years with more data, drag "Pub Date" (from the Tables section) over Filters and select "Years" in the popup. Click on the "Condition" tab -> "By field," and change = to > 10. Click "Ok." Now, our line graph has updated so that only years where at least 10 books were published will be visible.
4. To see the breakdown by genre, drag "Genre" over "Color" as we did before. 

### Map: Where Authors were Born
1. Click on the new sheet icon to open a new, blank workspace.
2. Double click on "Birthplace" to see a map of where almost all authors in our dataset were born. In the lower right, click on "2 unknown" to see which locations Tableau doesn't recognize -> "Edit Locations." Tableau doesn't recognized "England" and "Scotland" because it's looking for "United Kingdom." Double click on "Unrecognized" and type "United Kingdom" to create a mapping for Tableau between the words so that it will know where to locate our data points. Then click "Ok." Now all of our data has been mapped.
3. To see how the locations change over time, drag "Pub Date" over "Pages." Click on "Format" in the top toolbar -> "Animations." Select "Off" and "X" out of the animation pane. For the "YEAR(Pub Date) legend," click "Show History" and turn on "Last" under "Length" so that dots won't immediately disappear from view when the year changes. Click the triangle play button to watch the dots change. To alter the speed, click on the stack rectangle symbols (three rectangles is the fastest speed).
4. To give our map access to additional information that we will use later when making our dashboard, drag the "Book Title" and "Book Fullurl" pills over the "Tooltip" mark.
5. To give a title to the map, double click on the title as before, but don't remove "\<Page Name>" because that will automatically populate our title with whatever year is showing.
6. To see only books published since 1900, try creating a "Pub Date" filter (see the steps from the line graph we made if you get stuck).

### Data Dashboard: Bring Visualizations Together
Let's pull our visualizations together in a data dashboard.
1. Start a data dashboard by clicking on the icon next to the new sheet icon.
2. Adjust the size of the dashboard by clicking on the dropdown under "Size" in the left-hand column. This enables you to re-size for the device(s) you're designing for. To have the dashboard take up the size of the screen you're using at this moment, click the size dropdown and then click the dropdown by "Range" and select "Automatic."
3. Double click on the sheet names in the left-hand column to add them to the dashboard (I would start with the map). You can also drag and drop. Practice re-arranging them on the dashboard.
4. To make the dashboard even more dynamic and informative, let's add a component that links out to the Goodread's webpage for the book a user hovers over when looking at the map.
- Drag a "Web Page" object onto the dashboard and click "Ok" without adding a URL. 
- On the dropdown box for the web page object, click "Add URL Action."
- In the name field, type: "Go to Goodreads Website."
- For "Run action on," choose "Hover."
- Check the box so that only the map worksheet is selected.
- For the URL, click on triangle  and select "ATTR(Book Fullurl)."
- Click "Ok" and "Ok" again to add the action.
- Now when you hover over any data point on the map, the webpage should automatically update to reflect the book that's selected, unless the dot on the map represents more than one book, in which case the page won't update.

### Save Your Work
To save your Tableau workbook, you have to create a free Tableau account. When you click save, you will be prompted to log in and save your workbook to Tableau's server, where it will be visible on Tableau Public. Users can interact with your workbook on Tableau Public, or they could download, add to, or otherwise edit it. Remember, your data also becomes public, unless you're working with Tableau Dekstop! 

## Next Steps, Cautions, & Additional Tips
* To learn about joining multiple datasets, creating data stories, running calculations, and managing a Tableau server, watch Tableau's free [online training videos](https://www.tableau.com/learn/training/20201).
* Word of caution: Tableau frequently has updates available, but they're not always backwards compatible. For that reason, you might not want to update to the newest version while you're in the middle of a project.
* For additional practice and open datasets, check out [#MakeoverMonday](https://www.makeovermonday.co.uk/). Every week, Tableau shares a dataset and starter visualization, challenging participants to remake it. You can find the results and share your remakes on [Twitter](https://twitter.com/hashtag/makeovermonday?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Ehashtag). Better yet, if you see a makeover visualization someone else created that you like, try downloading the workbook from Tableau Public to see how they made it!
