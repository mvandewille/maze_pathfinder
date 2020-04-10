# Repository for work related to Group 20's Maze Pathfinding project

To run the application, simply open index.html within the "pathfinding" folder.

The project is built using pure JavaScript, HTML, and CSS styles.

The interface consists of a toolbar, grid display, and a console window.

From the interface, a user can either create their own maze using the Place Wall button or generate a random maze by selecting the Generate Maze button.
Then, the user can place a start and end point and select the pathfinding algorithm they would like to use. Once a start point, end point, and algorithm have been selected, the user can begin the visualization by selecting "Start Visualization". 

Messages or errors will be displayed in the console window to show the user if an action has completed successfully or if more steps are needed. Once a visualization is finished, the user can clear the entire grid using the Clear All button and begin a new visualization without reloading the webpage.

Before the visualization begins, the program will also verify that a valid path exists between the start node and end node and will alert the user in the console to create a new grid.

The randomized maze generator uses a variation of Prim's Algorithm, an algorithm used to generate a minimum spanning tree from an undirected graph. With this algorithm,
a binary maze is created so that any cell within the maze is either a wall or passage. The algorithm is guaranteed to create a solvable maze, i.e. any point in the maze can be reached by any other.

For our pathfinding algorithms we have chosen A*, Dijkstra's algorithm, and Sample pathfinding algorithm. These all work in somewhat unique ways, and this is apparent through the visualization:

 - Sample algorithm begins at the endpoint and branches throughout the entire maze, assigning a "counter" value to every node it visits that is equal to the distance from the end node. Then, once the start node is found, it begins at the start and selects the neighboring cell with the lowest counter until the end point is reached.
 - Dijkstra's algorithm also branches throughout the entire maze to find the path, but unlike Sample it begins at the start node and assigns each cell a "parent" rather than a counter value. Once the end is reached, the algorithm follow's each cell's parent from the start node to the end node.
 - A* is similar to Dijkstra's algorithm, but with an added heuristic that allows it to "know" where the end node is. This algoritm adds the distance from the start node to the calculated heuristic value for each cell, then follows a path based on the least total cost. For our heuristic calculation, we elected to use Manhattan Distance, which is the sum of absolute values of differences in the goal’s x and y coordinates and the current cell’s x and y coordinates respectively.

Finally, as an added feature to the visualization, as each algorithm visits cells further away from the start node, the cells will turn varying colors to signify a gradient between the start point color and the end point color.
This gradient is calculated before the algorithm runs and is always proportional to the distance of the path from start to end.
