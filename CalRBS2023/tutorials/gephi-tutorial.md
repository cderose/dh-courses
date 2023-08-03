[Sample datasets](https://github.com/gephi/gephi/wiki/Datasets)

# Navigate the Gephi Interface

The Overview pane is where you'll spend most of your time in Gephi. This is where you can experiment with different layouts, color or resize nodes according to some property or measure, run statistics, and partition the network based on a parameter you select.  

If you ever remove one of the windows on the Overview pane or need to reset how they're sized, click on the "Windows" toolbar at the very top of your computer pane, and select "Reset Windows."

<p align="center"><img width="700" height="350" src="https://github.com/cderose/dh-courses/blob/master/images/gephi-overview.png"></br>Overview Tab</p>

The Data Laboratory is where you can import, edit, and view your data. Although they don't look like buttons, you can click on "Nodes" and "Edges" to move between the two spreadsheets.  

When importing your data into Gephi, begin with the node list first ("Add node" button), followed by the edge list ("Add edge" button).

<p align="center"><img width="700" height="350" src="https://github.com/cderose/dh-courses/blob/master/images/gephi-dataLab.png"></br>Data Laboratory</p>

The Preview pane is where you can prepare your network for publication. It gives you some design control over the look of your network (for example, how the node labels appear and whether the edges are curved or straight). Keep in mind that design choices affect the interpretability of the network.

There are two buttons to be aware of on this page:
- Refresh needs to be clicked to first view the network in the Preview pane and then to view any changes you make to the Presets.
- Export SVG/PDF/PNG lets your export a copy of your visualization so that you can either keep designing it in other tools (like Photoshop or Illustrator) or so you can have a static image that you can add to a paper or website.
<p align="center"><img width="700" height="350" src="https://github.com/cderose/dh-courses/blob/master/images/gephi-publish.png"></br>Preview Tab</p>

# Create a workspace
Gephi does *not* have an undo button. As a result, it's a good idea to duplicate your workspace after you've uploaded your graph (and then whenever you make a meaningful update) so that if something goes awry, you don't have to start over completely.  

You can create a workspace a couple ways.
- From the Workspace tab at the top, click Duplicate.
- From the Data Laboratory pane, select all of your nodes (you can use control or command A), right click, and then select Copy to -> New workspace.  

# Choose a layout
From the Overview pane, you can click on the "Layout" tab to find an optimal layout for your network. Frequently used layouts include the following:  

**ForceAtlas 2** – Turns the layout into a magnetic field. Nodes that aren't connected repel; edges act like spring that pull together.  For settings, try Stronger Gravity (or your isolates will fly away), Dissuage Hubs, and Prevent Overlap.  
**Fruchterman Reingold** – Mimics the movement of charged particles. Useful for large, undirected networks.  

After you find a layout you like, you might additionally run one of the layouts below.  
**Expansion** – Enlarges the network.  
**Contraction** – Contracts the network.  
**Label Adjust** – Makes the labels more presentable.  

# Run statistics
From the Overview pane, you can click on the "Statistics" tab to run various statistics that can help you make sense of a graph. The following are a few of the more popular statistics you might run:  

**Betweenness centrality** – Measures how often a node is on the shortest path to any other node in the network. Nodes with a high betweenness centrality are strategically positioned within the network.  
**Modularity** – Detects communities (or subgroups) within the network.  
**Eigenvector centrality** – Measures a node's influence in a network based on that node's connections.  

Whenever we run a statistic, the results become available in the "Appearance" section over the Overview pane. They also appear in our data spreadsheets in the Data Laboratory.

# Filter data
1. From Statistics, run Average Degree. This step makes the indegree, outdegree, and degree information available for coloring, sizing, or filtering nodes.
2. From Filters, click Topology and then Degree Range to the Queries section at the bottom of the Filters pane.
3. Adjust the slider to determine the minimum or maximum connections a node must have to be visible in the network. (Don't forget to click Stop on the filter after you're finished.)

# Create a time slider
To visualize how our network changes over the course of the play, we can create a time slider.  
1. From the Data Laboratory pane, click on "Edges" and then "Merge columns".
2. In the popup that appears, select "act_scene" and click the right arrow.
3. Click the "Join values with separator" dropdown, and select "Create time interval".
4. Click "Ok" and then click to "Enable Timeline" at the bottom of the Data Laboratory pane.
We now have a time slider! This slider also acts as a filter. If we narrow the slider so that it only shows Act I connections, any statistics we run will only apply to those connections.

