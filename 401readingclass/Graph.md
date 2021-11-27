# Graph

* A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

- Here is some common terminology used when working with Graphs:

> Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.

> Edge - An edge is a connection between two nodes.

> Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.

> Degree - The degree of a vertex is the number of edges connected to that vertex.


<br>

<p>A graph is a non-linear data structure that can be looked at as a collection of <code class="language-plaintext highlighter-rouge">vertices</code> (or <code class="language-plaintext highlighter-rouge">nodes</code>) potentially connected by line segments named <code class="language-plaintext highlighter-rouge">edges</code>.</p>

<p>Here is some common terminology used when working with Graphs:</p>

<ol>
  <li><em>Vertex</em> -  A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.</li>
  <li><em>Edge</em> - An edge is a connection between two nodes.</li>
  <li><em>Neighbor</em> - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.</li>
  <li><em>Degree</em> - The degree of a vertex is the number of edges connected to that vertex.</li>
</ol>

<h2 id="directed-vs-undirected">Directed vs Undirected</h2>

<h3 id="undirected-graphs">Undirected Graphs</h3>

<p>An <code class="language-plaintext highlighter-rouge">Undirected Graph</code> is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.</p>

<p>For example, in the graph below, Node <code class="language-plaintext highlighter-rouge">C</code> is connected to <code class="language-plaintext highlighter-rouge">Node A</code>, <code class="language-plaintext highlighter-rouge">Node E</code> and <code class="language-plaintext highlighter-rouge">Node B</code>.
There are no “directions” given to point to specific vertices. The connection is bi-directional.</p>



<p>The undirected graph we are looking at has 6 vertices and 7 undirected edges.</p>

<p>Vertices/Nodes = {a,b,c,d,e,f}</p>

<p>Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}</p>

<h3 id="directed-graphs-digraph">Directed Graphs (Digraph)</h3>

<p>A <code class="language-plaintext highlighter-rouge">Directed Graph</code> also called a <code class="language-plaintext highlighter-rouge">Digraph</code> is a graph
where every edge is directed.</p>

<p>Unlike an undirected graph, a <code class="language-plaintext highlighter-rouge">Digraph</code> has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.</p>

<p>Compare the visual below with the undirected graph above. Can you see the difference? The <code class="language-plaintext highlighter-rouge">Digraph</code> has arrows pointing to specific nodes.</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)

<p>The directed graph above has six vertices and eight directed edges</p>

<p>Vertices = {a,b,c,d,e,f}</p>

<p>Edges = {(a,c),(b,c),(b,f),(c,e),(d,a),(d,e)(e,c)(e,f)}</p>

<h2 id="complete-vs-connected-vs-disconnected">Complete vs Connected vs Disconnected</h2>

<p>There are many different types of graphs. This depends on how connected the graphs are to other node/vertices.</p>

<p>The three different types are completed, connected, and disconnected.</p>

<h3 id="complete-graphs">Complete Graphs</h3>

<p>A complete graph is when all nodes are connected to all other nodes.</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)


<p>Take a close look at each of the vertices in the graph above. Do you notice that each vertex is actually connected to every other node on the graph? That is what makes it a complete graph.</p>

<h3 id="connected">Connected</h3>

<p>A connected graph is graph that has all of <code class="language-plaintext highlighter-rouge">vertices</code>/<code class="language-plaintext highlighter-rouge">nodes</code> have at least one edge.</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/CompleteGraph.PNG)

<p>In the visual above, this looks a lot more than what you are used to seeing. If you look closely at the different vertices of the graph, you will see that each node is connected to at least one other node or vertices. A <code class="language-plaintext highlighter-rouge">Tree</code> is a form of a connected graph. We will talk more about that in a bit.</p>

<h3 id="disconnected">Disconnected</h3>

<p>A disconnected graph is a graph where some vertices may not have edges.</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/ConnectedGraph.PNG)

<p>In the above visual, the disconnected graph shows that some nodes may not always be connected to other nodes or vertices of the graph. It is complelty possible to have standalone nodes or edges (also known as islands) in a graph data structure.</p>

<h2 id="acyclic-vs-cyclic">Acyclic vs Cyclic</h2>

<p>In addition to undirected and directed graphs, we also have
acyclic and cyclic graphs.</p>

<h3 id="acyclic-graph">Acyclic Graph</h3>

<p>An acyclic graph is a directed graph without cycles.</p>

<p>A cycle is when a node can be traversed through and potentially end up back at itself.</p>

<p>Here is an example of 3 acyclic graphs:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DisconnectedGraph.PNG)

<p>A directed acyclic graph is also called a DAG. This can also be represented as what we know as a <strong>tree</strong>.</p>

<h3 id="cyclic-graphs">Cyclic Graphs</h3>

<p>A Cyclic graph is a graph that has cycles.</p>

<p>A cycle is defined as a path of a positive length that starts and ends at the same vertex.</p>

<p>Here is an example of a two different cyclic graph:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/threeAcyclic.png)

<h2 id="graph-representation">Graph Representation</h2>

<p>We represent graphs through:</p>

<ol>
  <li>Adjacency Matrix</li>
  <li>Adjacency List</li>
</ol>

<p>We will represent the following graph as both an Adjacency Matrix and an Adjacency List:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/cyclic.PNG)

<h3 id="adjacency-matrix">Adjacency Matrix</h3>

<p>An Adjacency matrix is represented through a 2-dimensional array.
If there are <em>n</em> vertices, then we are looking at an <em>n x n</em> Boolean matrix</p>

<p>Each Row and column represents each vertex of the data structure.
The elements of both the column and the row must add up to 1 if there is an edge that connects the two, or zero if there isn’t a connection.</p>

<p>This is what an adjacency matrix looks like:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)

<p>A few things to note from the above:</p>

<ol>
  <li>Looking at the graph we are representing, you can see that <code class="language-plaintext highlighter-rouge">Vertex A</code> connects to both
<code class="language-plaintext highlighter-rouge">Vertex D</code> and <code class="language-plaintext highlighter-rouge">Vertex C</code>. To show this, we place a <code class="language-plaintext highlighter-rouge">1</code> in the position of <code class="language-plaintext highlighter-rouge">(a,c)</code> and <code class="language-plaintext highlighter-rouge">(a,d)</code>.</li>
  <li>We follow this same pattern for the other vertex’s and where they are connected.</li>
  <li>If there is not an edge/connection between the vertex’s, we represent this by placing a <code class="language-plaintext highlighter-rouge">0</code> in the appropriate point of
 the matrix.</li>
</ol>

<p>a <strong>sparse</strong> graph is when there are very few connections.
a <strong>dense</strong> graph is when there are many connections</p>

<p>Within an adjacency matrix, an undirected graph will always be symmetric. This is not the case for a directed graph.</p>

<h3 id="adjacency-list">Adjacency List</h3>

<p>An adjacency list is the most common way to represent graphs.</p>

<p>An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.</p>

<p>Adjacency lists make it easy to view if one vertices connects to another.</p>

<p>This is what an Adjacency List looks like:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjMatrix.PNG)

<p>Looking at the original graph that we are representing, we can see that <code class="language-plaintext highlighter-rouge">Vertex A</code> has an edge to both <code class="language-plaintext highlighter-rouge">Vertex C</code> and <code class="language-plaintext highlighter-rouge">Vertex D</code>.
As a result, we will place both <code class="language-plaintext highlighter-rouge">Vertex C</code> and <code class="language-plaintext highlighter-rouge">Vertex D</code> in the adjacency list. Just from observation, we can see that we will only place the vertices that are connected in the list. If there is no connection between the vertices, they are not listed.</p>

<p>Thinking about how we will implement this in code? Well, let’s look at what the visual is telling us.</p>

<ol>
  <li>We can visually see that we are working with a collection of some sort. The visual is depicting a <em>Linked List</em>, but you could easily make it an <em>array of arrays</em> if you’d like.</li>
  <li>Each index or node (depending on the data structure you choose to represent the adjacency list) will be a vertex within the graph.</li>
  <li>Every time you <strong><em>add an edge</em></strong>, you will find the appropriate vertices in the data structure and add it to the appropriate location.</li>
</ol>

<h2 id="weighted-graphs">Weighted Graphs</h2>

<p>A weighted graph is a graph with numbers assigned to its edges.
These numbers are called weights. This is what a weighted graph looks like:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjList.PNG)

<p>When representing a weighted graph in a matrix, you set the element in the 2D array
to represent the actual weight between the two paths. If there is not a connection between the two vertices, you can put a <code class="language-plaintext highlighter-rouge">0</code>, although it is known for some people to put the infinity sign instead.</p>

<p>Using the graph from above, here is an example of what a <code class="language-plaintext highlighter-rouge">weight matrix</code> would look like:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightGraph.PNG)

<p>Within adjacency lists, you must include <em>both</em> the weight and the name of the adjacent vertex.</p>

<p>Here is an example of what this may look like:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightMatrix.PNG)

<p>Do you notice the differences and similarities of a weighted adjacency list vs an unweighted? A great way to represent the {vertices, weight} connection is through some sort of key/value pair data structure.</p>

<h2 id="traversals">Traversals</h2>

<p>You will be required to traverse through a graph. The traversals
itself are like those of trees. Below is a breakdown of how you would traverse a graph.</p>

<h3 id="breadth-first">Breadth First</h3>

<p>In a breadth first traversal, you are starting at a specific vertex/node. This node must be specified when
calling the <code class="language-plaintext highlighter-rouge">BreadthFirst()</code> method. The breadth-first traversal of a graph is like that of a tree, with the exception
that graphs can have cycles. Traversing a graph that has cycles will result in an infinite loop….this is bad. To prevent such behavior, we need to have some way to keep track of whether a vertex has been “visited” before. Upon each visit, we’ll add the previously-unvisited vertex to a <code class="language-plaintext highlighter-rouge">visited</code> set, so we know not to visit it again as traversal continues.</p>

<p>As a refresher of what breadth first actually means here it is:
Breadth first traversal is when you visit all the nodes that are closest to the root as possible. From there you traverse
outwards, level by level, until you have visited all the vertices/nodes.</p>

<p>Here is what the algorithm breadth first traversal looks like:</p>

<ol>
  <li><code class="language-plaintext highlighter-rouge">Enqueue</code> the declared start node into the Queue.</li>
  <li>Create a loop that will run while the node still has nodes present.</li>
  <li><code class="language-plaintext highlighter-rouge">Dequeue</code> the first node from the queue</li>
  <li>if the <code class="language-plaintext highlighter-rouge">Dequeue</code>‘d node has unvisited child nodes, add the unvisited children to <code class="language-plaintext highlighter-rouge">visited</code> set and insert them into the queue.</li>
</ol>

<p>Let’s look at a visual for a breadth first:</p>


<p>The visual above shows the levels in which the nodes will be added to the queue. You can see that since the root node is <code class="language-plaintext highlighter-rouge">A</code>, it will look the nodes that are only 1 away from the root. This is
 <code class="language-plaintext highlighter-rouge">C</code>,<code class="language-plaintext highlighter-rouge">E</code>, &amp; <code class="language-plaintext highlighter-rouge">B</code>.</p>

<p>Next it will look at the nodes that are 2 away from the root, this is <code class="language-plaintext highlighter-rouge">F</code>, <code class="language-plaintext highlighter-rouge">G</code>, &amp; <code class="language-plaintext highlighter-rouge">D</code>. It will follow this pattern until it reaches the end of the graph and all nodes have been visited.</p>

<p>Look at the code below to take a closer look at what is actually happening.
This is the code for a breadth first traversal:</p>




</code></pre></div></div>

<p>Here is a breakdown of what is going on:</p>

<ol>
  <li>We have declared that our starting node (or root) is going to be <code class="language-plaintext highlighter-rouge">Node A</code>.</li>
  <li>The first thing we want to do is <code class="language-plaintext highlighter-rouge">Enqueue</code> the root.</li>
  <li>We also need to add the root to the <code class="language-plaintext highlighter-rouge">visited</code> set.</li>
  <li>Next, we enter a while loop. We want this loop to keep running until there are no more nodes in our queue.</li>
  <li>Once we are in the while loop, we want to <code class="language-plaintext highlighter-rouge">Dequeue</code> the front node and then check to see if it has any children.</li>
  <li>if there are children of the node we are currently looking at, we want to add them to <code class="language-plaintext highlighter-rouge">visited</code> set. This will help us know that we have already seen that node before, and won’t accidently push us into an infinite loop if the graph was cyclic. In addition to tracking each child node as visited, we want to place any of its children that have not yet been visited
into the queue.</li>
  <li>The process will complete until the queue is empty.</li>
  <li>Once the while loop breaks, we can then return the list of nodes. This list
will contain, in order, all the nodes that were traversed.</li>
</ol>

<p>A few things to note about breadth-first traversals:</p>

<ol>
  <li>If there are any disconnected nodes (such as islands) with the graph data structure, they will not be traversed.</li>
  <li>Breadth-first only outputs the nodes that are connected in some relation to the root that you pass in.</li>
</ol>

<h3 id="depth-first">Depth First</h3>

<p>In a depth first traversal, we approach it a bit different than the way we do when working with a depth first traversal of a tree. Similar to how the breadth-first uses a queue, we are going to use a Stack for our depth-first traversal.</p>

<p>The algorithm for a depth first traversal is as follows:</p>

<ol>
  <li><code class="language-plaintext highlighter-rouge">Push</code> the root node into the stack</li>
  <li>Start a while loop while the stack is not empty</li>
  <li><code class="language-plaintext highlighter-rouge">Peek</code> at the top node in the stack</li>
  <li>If the top node has unvisited children, mark the top node as visited, and then
<code class="language-plaintext highlighter-rouge">Push</code> any unvisited children back into the stack.</li>
  <li>If the top node does not have any unvisited children, <code class="language-plaintext highlighter-rouge">Pop</code> that node off the stack</li>
  <li>repeat until the stack is empty.</li>
</ol>

<p>Let’s look at the visual for a depth-first traversal.</p>

<p>We will conduct a depth-first traversal on this graph:</p>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/BreadthFirst.PNG)

<ol>
  <li>The first thing that we are going to do is look at the root. Following
the algorithm we described above, we want to look at all of <code class="language-plaintext highlighter-rouge">Node A</code>’s children (<code class="language-plaintext highlighter-rouge">Node B</code> and <code class="language-plaintext highlighter-rouge">Node D</code>). Since <code class="language-plaintext highlighter-rouge">Node B</code> is first, we notice that it has not yet been visited, it then gets
<code class="language-plaintext highlighter-rouge">Pushed</code> into the stack.</li>
  <li>Before looking at the rest of <code class="language-plaintext highlighter-rouge">Node A</code>’s children, we will look at the children of <code class="language-plaintext highlighter-rouge">Node B</code>. and start visiting children that haven’t yet been visited.</li>
  <li><code class="language-plaintext highlighter-rouge">Node C</code>  then gets <code class="language-plaintext highlighter-rouge">Pushed</code> into the stack.</li>
  <li>By the time we hit <code class="language-plaintext highlighter-rouge">Node G</code>, This is the state of our data structure:</li>
</ol>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/Depth1.PNG)

<ol>
  <li>Moving back up the graph, we slowly <code class="language-plaintext highlighter-rouge">Pop</code> off the stack until we reach a child node that has not yet been visited. This just so happens to be <code class="language-plaintext highlighter-rouge">Node D</code>, since it is connected to <code class="language-plaintext highlighter-rouge">Node B</code>.</li>
  <li>The algorithm keeps running and once we hit <code class="language-plaintext highlighter-rouge">NodeE</code>, this is the state of our program:</li>
</ol>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/Depth2.PNG)

<ol>
  <li>Notice how <code class="language-plaintext highlighter-rouge">Node D</code> has 3 children. We already visited <code class="language-plaintext highlighter-rouge">Node E</code>, so we move onto <code class="language-plaintext highlighter-rouge">Node H</code>.</li>
</ol>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/depthTrav3.PNG)
<ol>
  <li>Finally, we can see that <code class="language-plaintext highlighter-rouge">Node H</code> has a child, so we can wrap up the traversal by visiting <code class="language-plaintext highlighter-rouge">Node F</code>.</li>
</ol>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/depthTrav4.PNG)

<ol>
  <li><code class="language-plaintext highlighter-rouge">Node F</code> gets popped off the stack since it has no children</li>
  <li>All three of the children of <code class="language-plaintext highlighter-rouge">Node D</code> have been visited so it also gets <code class="language-plaintext highlighter-rouge">Pop</code>‘d off the stack</li>
  <li>Finally, <code class="language-plaintext highlighter-rouge">Node A</code> gets popped off the stack to complete the algorithm.</li>
</ol>

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/depthTrav5.PNG)

<h2 id="real-world-uses-of-graphs">Real World Uses of Graphs</h2>

<p>Graphs are extremely popular when it comes to it’s uses. Here are just
a few examples of graphs in use:</p>

<ol>
  <li>GPS and Mapping</li>
  <li>Driving Directions</li>
  <li>Social Networks</li>
  <li>Airline Traffic</li>
  <li>Netflix uses graphs for suggestions of products</li>
</ol>

<p>There is a lot to graphs, and a lot you can do with them. Let this be document be used as an introduction to graphs. There is a lot more to them then described, so start exploring, and have fun with them!</p>
  </body>
</html>
