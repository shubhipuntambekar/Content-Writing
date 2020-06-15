---


---

<h1 id="dijkstras-algorithm">Dijkstra’s Algorithm</h1>
<p>Edsger W. Dijkstra in the year 1956 came up with an algorithm to find shortest path between two nodes in a graph. Dijkstra’s algorithm (and its many variations) can be used to find the shortest path between any two points. This algorithm is also called Single source shortest paths problem.</p>
<p>For instance, the GPS system of you car makes use of a (variation of) Dijkstra’s Algorithm to minimize the time your trip takes to reach a destination. Also, information that is sent over the Internet makes use of Dijkstra’s algorithm to route this information from router to router until it find its final destination.</p>
<h4 id="how-does-the-algorithm-works">How does the algorithm works?</h4>
<p>Dijkstra’s Algorithm uses a greedy approach assuming that if we find the next best solution and repeat the same for every other node, this will result in the best solution for the whole program.<br>
Connected Weighted Graph G = (V,E)<br>
<strong>Step 1:</strong> Initially create an empty set (<em>sPath</em>) to keep track of all the vertices that are included in the shortest path tree.<br>
<strong>Step 2:</strong> Assign a distance value to all the vertices. Initialize all vertices distance to infinity, except for the source vertex. Set the distance value for source vertex to 0 so that it is picked first.<br>
<strong>Step 3:</strong> Repeat step 4 and step 5 while the set (<em>sPath</em>) doesn’t contain all the vertices.<br>
<strong>Step 4:</strong> Pick a vertex <em>u</em> having minimum distance which is not present in the set <em>sPath</em> and include it into <em>sPath</em>.<br>
<strong>Step 5:</strong> Update distance values for all the adjacent vertices of picked vertex <em>u</em>. For every adjacent vertex <em>v</em>, if the sum of distance value of <em>u</em> (from source) and weight of edge (u,v) is less than distance value of <em>u</em>, then update the adjacent vertex <em>u</em>’s distance.</p>
<h4 id="example">Example</h4>
<ol>
<li>
<p>Start with a weighted graph.<br>
<img src="https://i.ibb.co/PF9M66b/IMG20200614130722.jpg" alt="Start with a weighted graph"></p>
</li>
<li>
<p>Initialize all vertices distance to infinity, except for the source vertex.<br>
<img src="https://i.ibb.co/xmWN4np/IMG-20200614-134130.jpg" alt="Initializing distance values for all vertices"></p>
</li>
<li>
<p>Go to each adjacent vertex and update its distance accordingly. Here minimum distance vertex = 0 and adjacent nodes are updated to (0+2), and (0+4).<br>
<img src="https://i.ibb.co/sWCYyhf/IMG-20200614-134115.jpg" alt="enter image description here"></p>
</li>
<li>
<p>Select minimum vertex distance node which is not in sPath and add to sPath. Here the node is 2. Update the distance value for all its adjacent nodes.<br>
<img src="https://i.ibb.co/yBQ0hqV/IMG-20200614-134057.jpg" alt="Updating node values of adjacent nodes of 2"></p>
</li>
<li>
<p>Select minimum vertex distance node which is not in sPath and add to sPath. Here the node is 3. Update the distance value for all its adjacent nodes.<br>
<img src="https://i.ibb.co/H4GXJND/IMG-20200614-134031.jpg" alt="Updating node values of adjacent nodes of 3"></p>
</li>
<li>
<p>Select minimum vertex distance node which is not in sPath and add to sPath. Here the node is 6. Update the distance value for all its adjacent nodes.<br>
<img src="https://i.ibb.co/64sxjhm/IMG-20200614-134010.jpg" alt="Updating node values of adjacent nodes of 8"></p>
</li>
<li>
<p>Select last available vertex and add it to sPath. As we can see it does not have any adjacent vertex, we can end our loop with the final result, i.e. shortest path from selected vertex to all the other vertices.<br>
<img src="https://i.ibb.co/ccTWMDz/IMG-20200614-133954.jpg" alt="Shortest path from selected node"></p>
</li>
</ol>
<h4 id="things-to-keep-in-mind">Things to keep in mind</h4>
<ol>
<li>Avoid updating distance values of the vertices that are already present in set (sPath).</li>
<li>This algorithm calculates the shortest distance, but not the path information.</li>
<li>This algorithm may or may not work on negative weighted graphs.</li>
</ol>
<h4 id="code">Code</h4>
<h4 id="time-complexity--ov2">Time Complexity : O(V^2)</h4>
<p>The time complexity of this problem can be improved by using an adjacency list instead of adjacency matrix. The Adjacency list implementation can be done using a Priority Queue (Min), and a time complexity of O(E log V) can be achieved using this.</p>
<h4 id="applications">Applications</h4>
<ol>
<li>Finding shortest path</li>
<li>Finding directions for a location in a map</li>
<li>Used in social networking applications</li>
<li>Used in a telephone network/routing network</li>
</ol>

