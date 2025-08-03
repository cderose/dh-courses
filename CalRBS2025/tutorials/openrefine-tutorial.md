# Cleaning Data with OpenRefine

 ## Create a project and set up your workspace
1.	Launch OpenRefine.   
The following links can be helpful to have on hand as we work through the activities:
- You can re-access the webpage from http://127.0.0.1:3333/ or localhost: 3333  
- You can also access your OpenRefine preferences at http://127.0.0.1:3333/preferences.

2.	Load in the Directory of Open Access Journals dataset by going to Create project -> This Computer -> Choose Files. Click Next.
This dataset comes from the Library Carpentry.
- Create project

3.	See how OpenRefine is interpreting the dataset.
- Experiment with changing the settings.
- Change Parse Next from 1 to 0 and see how that affects your header row. Change the value back to 1.

4.	Give the project a name and a tag.
For the name, I typically add something like "cleaned" or transformed" to the end of the filename to indicate that I've edited the file in some way.
The tag will allow you to search for the project among your other OpenRefine projects.

5. Click Create project to open the project workspace.  
OpenRefine displays data as tables. You can adjust how many rows are displayed at a given time.
A row/record represents a single observation (such as a journal article).
A column represents a variable or feature.  

6. To reorder columns, click the All dropdown -> Edit columns -> Re-order columns.
Move the language column up so that it follows the author column.

## Explore values with text faceting
Text faceting is one of the most useful features for getting a closer look at a column.

1. To text facet by author, click the Authors dropdown -> Facet -> Text facet.
The facet view shows all that values in that column. You can sort these values alphabetically or by count (frequency).  

Do you notice any challenges with how the values are currently organized?  
Several cells contain multiple authors, which makes it difficult to glean information about any single author.  
Happily, the authors use a consistent delimitor or separator - in this case, it's the pipe (|) symbol. OpenRefine makes it easy to divide cells so long as they have a consistent symbol.

2. To divide the authors so that there's only one author per cell, click the dropdown by ‘Authors’ and select ‘Edit cells’ -> ‘Split multi-valued cells’  
When OpenRefine asks what separator to use, add the pipe symbol (|) and click ‘Ok’.  
Notice that Rows and Records values have changed. Records represent a single journal article whereas rows have expanded because of the multiple authors.  

Now if we look at the count in our text facet, we can see we have too many to display. Select the button to set the display limit and change to 3000.  (You can then increase or decrease this number at any time by changing it from your OpenRefine preferences at http://127.0.0.1:3333/preferences - OpenRefine will remember your preferences between sessions.)  

Looking at our author text facet, we can now sort authors by count and see that Akkurt is the most published author in our dataset.  

If we want to work with our spreadsheet like this, we can go to All - > Edit Columns -> Fill Down to populate the spreadsheet so that the article information trickles down for all author rows.  

You can go to the Undo/Redo tab at any time to undo a decision. The Undo/Redo section also gives you the ability to export a JSON file that outlines all the changes you made. You can share this colleague with collaborators, save it for your own records, or save it and then import it into another OpenRefine project if you have data that will need similar updates.

3.	Join the author cells back together for now. Although we could do this by going to Undo/Redo and undoing the step where we split them up, let's look at another way for merging cells.  

Click the dropdown by ‘Authors’ and go to ‘Edit cells’ -> ‘Join multi-valued cells’. When asked for the separate, add the pipe symbol (|) and click Ok.  

It's important to choose the separator carefully. You should avoid choosing a separator that might appear in your data (such as a commma or period). If we had chosen a period as the separator for the author names, what issue would we have if we tried to split the cells again? (Some of the author names have initials.)


## Practice with faceting

Text faceting is a great way to get a quick overview of data in a given column. It’s also useful for changing a group of values with only a couple clicks.  

1. Apply a text facet for the Language column. Click the Language dropdown and go to -> Facet -> Text facet.  

What inconsistencies or data gaps did that reveal?
- EN and English
- Blank values  

To change English (which occurs 107 times) to EN, click on English and then -> Edit -> type EN and click Apply. In that quick step, we were able to standardize over a hundred records. This feature is especially handy if you have multiple contributors adding data to a spreadsheet and an increased risk of different conventions or terms.  

2. You can also use text faceting to filter your data. For example, click on Blank to see the 15 blank columns. If you knew the language for those texts, you could add it to each individual cell by hovering over the cell and click on Edit.  

If you don't know the language for those cells, you could opt to remove them from the dataset. While you have only the Blank cells selected, you can click the All dropdown to go to Edit rows -> Remove matching rows. (If you try this and you'd like to get them back, go to Undo/Redo.)

Additionally, you could go to Export to export a spreadsheet of all the blank values to add them back into your data collection pipeline. 

Or if you only want to work with French and Spanish articles, you can filter to just those articles by Click on ES in the text facet and the hover over clicking include next to FR.  

## EXERCISE 1: Text faceting 
Use text faceting to answer the following questions:
- What is the second most common CC license in the dataset?
	License -> facet -> text facet -> sort by count  
	Answer: CC BY-NC-ND - attribution, non-commercial, no derivatives  
- How many articles in the file don’t have a license assigned?
	Answer: 6  

Another way you could do find this information is with a customized facet. To create a customized facet, click the License dropdown and select Facet -> Customized facet -> Facet by blank. This step returns boolean values where True means there's is a blank cell and False means there is not a blank cell.


## Cluster similar values

Another useful feature that comes with text faceting is the cluster option. Clustering enables you to merge values based on text similarity. (How similarity is detected depends on the algorithms you select on the clustering screen.) For this reason, cluster is particularly effective in situations where you have minor variations in data values, such a C. Brontë and Charlotte Brontë.

1. Return to Author column and re-split values on the pipe separator. (Revisit the earlier steps for a refresher.)

2. Create a text facet.

3. From the text facet pane, click on the Cluster button. OpenRefine has identified several name variations that might refer to the same person (A Khan Vakeel v Vakeel A Khan).  

By default, OpenRefine will suggest merging values using the most frequent value. Or, if each variation occurs the same number of times, OpenRefine will suggest the value that is first alphabetically. You can always manually type in the desired value.

4. For this dataset, let’s click Select All -> Merge Selected & Re-Cluster. Now, OpenRefine says there are no more values to merge with the current settings. However, we can change what algorithm OpenRefine is using to identify similar values. For the details behind each option, see OpenRefine's documentation at: https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth

## Transformations

So far, we’ve been working with faceting and clustering, which are good for getting an overview of the data and standardizing values en masase. Transformations are another useful feature for reformatting our data. 

1. Create a text facet for the Publisher column. What values need to be updated?  

The MDPI AG entries are split into two groups, but to the human eye, they look identical. What's happening? It turns out, there's a blank space after one of the MDPI AG groups. You can see this blank space if you click Edit next to each group.  

Although we could fix this blank space by clicking Edit or Cluster, we can also use one of OpenRefine's prepared transformations - these transformations include several of the most common data preparation steps. One of those steps, is to remove all leading and trailing whitespace. 

2. Click the Publisher dropdown and go to Edit cells -> Common tranformations -> Trim leaning and trailing whitespace.  
MDPI AG is now automatically updated. Because it's very common for values to inadvertently have trailing whitespce, you might want to apply this common transformation to the whole dataset by repeating this step on the All column.  

Along with fixing whitespace, you can also change values to uppercase or lowercase. Before you adjust the case, it's important to know what tool or method you're planning to use with this dataset. For instance, with topic modeling, you might lowercase everything; however, with named entity recognition, you should leave the casing intact (where proper nouns are titlecased).

## EXERCISE 2: Commmon transformations
1. Split the Subjects column so each subject is on its own row.
2. Change all subjects to title case.
3. Describe what steps you might take next for standardizing the subjects.
4. Rejoin the multi-valued cells.

You could approach the above tasks as follows:
- Subjects dropdown -> Edit cells -> Split multi-valued cells
- Subjects dropdown -> Common transformations -> To titlecase
- Text facet -> Clustering
- Subjects -> Edit cells -> Join multi-valued cells on the pipe symbol

## Custom transformations: remove part of a value
In addition to prepared transformations, OpenRefine provides a way to write custom ones, giving us more fine-tuned control over our edits. For example, let's remove 'Pp' from the citation information. (Perhaps we're using MLA standards.)

1. Click on the Citation dropdown and create a text facet to take a closer look at the data.

2. Click on the Citation dropdown and select Edit cells -> Transform.

Custom transformations are typically written in what’s called a General Refine Expression Language (GREL), which functions similarly to regular expressions. (Older version of OpenRefine might call GREL the Google Refine Expression Language.)  

You can write GREL expressions in two different formats: 
- value.function(options)
- function(value, options)

Essentially, the value is what’s in your cell currently, the function is what you want to do to it, and the options are how you should make those changes.  

The Preview screen shows what the effects of your transformation will be on the cell. The History tab shows expressions you’ve run in the past, and the Starred tab let's you star expressions you might want to run again in the future. The Help tab inculdes a list of GREL functions. For additional help, you can visit the [OpenRefine Recipes page](https://github.com/OpenRefine/OpenRefine/wiki/Recipes) in GitHub. 

3.	To replace 'Pp', use the following expression: value.replace('Pp', '') and click Ok.

Spaces inside the quotation marks matter!  

4.	To star the expression we just used, go back to the transformations and star the function under History.

## Custom transformations: rearrange values in a cell

Let's return to our authors. Most appear to be listed by first name last name. How can we find out if any are reversed?  We can create a custom text facet that looks for a comma (as that's a good indication that the author is listed by last name first name).  

1. Click on the Authors dropdown and then click -> Facet -> Custom text facet. For the expression, use the following: value.contains(',') and hit Ok.

In the results, True means there is a comma in the cell. You can select True to take a closer look at the values and confirm that indeed, the authors are listed by last name first name.    

To fix the order, we can use another Transformation.

2. Click on the Authors dropdown and then select Edit cells -> Transform. For the expression, use the following: value.match(/(.*),(.*)/).reverse().join(' ')

- the / allows us to use a regular expression inside a GREL expression
- the .* matches any character 0 or more times  

This expression looks for any number of characters, followed by a comma, and then followed by any number of characters

If you end each function (match, reverse, join) one at a time, you'll see that the match function treats each value as an array or list [‘value’,’value2’, ‘value3’]. This step makes the individual pieces portable.  

THe reverse function reverses the order of the values, and the join function brings them back together as a string.  Make sure you have a space between the quotation marks in the join, or else there won't be a space in the author name.  

## Bonus step
Maybe we wanted all authors to be listed by last name first name. To do that, we can write another transformation.  

1.	Click on the Authors dropdown and then select Edit cells -> Transform. For the expression, use the following: value.match(/(.*)\s(.*)/).reverse().join(', ') 
- the / allows us to use a regular expression inside a GREL expression
- the .* matches one or more character
- the \s looks for white space

2.	Now that we’ve prepared our authors column, rejoin the author cells with the pipe symbol. (Review above if you'd like a refresher on the steps.)

3. Click on the Export dropdown to save our updated spreadsheet or to export the OpenRefine project itself.  

As a reminder, the Undo/Redo tab provides a help list of changes we made that we might want to keep as part of our project documentation. Click the Extract button to save the steps as a JSON file. At a future date, you or a collaborator can then use that JSON file to automatically apply those steps to another dataset. (To do so, go to Undo/Redo -> click Apply -> paste in the JSON information and then click Perform operations.)
