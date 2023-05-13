/**
 * Finds the shortest path between two points in a graph.
 *
 * @param {Object} graph - The graph object containing the nodes and edges.
 * @param {Object} start - The starting node.
 * @param {Object} end - The ending node.
 * @return {Array} - An array of nodes representing the shortest path from start to end.
 */
function findShortestPath(graph, start, end) {
  // Check if start and end nodes are valid
  if (!graph.nodes.includes(start) || !graph.nodes.includes(end)) {
    throw new Error('Start and end nodes must be valid nodes in the graph.');
  }

  // Initialize the queue with the start node
  let queue = [start];
  // Initialize the visited set with the start node
  let visited = new Set([start]);
  // Initialize the path map with the start node
  let pathMap = { [start]: [] };

  // While the queue is not empty
  while (queue.length > 0) {
    // Dequeue the first node
    let node = queue.shift();

    // If the node is the end node, return the path
    if (node === end) {
      return pathMap[node];
    }

    // Get the neighbors of the node
    let neighbors = graph.edges[node];

    // For each neighbor
    for (let neighbor of neighbors) {
      // If the neighbor has not been visited
      if (!visited.has(neighbor)) {
        // Add the neighbor to the visited set
        visited.add(neighbor);
        // Enqueue the neighbor
        queue.push(neighbor);
        // Set the path map for the neighbor
        pathMap[neighbor] = [...pathMap[node], neighbor];
      }
    }
  }

  // If the end node is not found, return null
  return null;
}
