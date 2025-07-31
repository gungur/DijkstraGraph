# DijkstraGraph Implementation

## Overview

This Java implementation provides a graph data structure with Dijkstra's shortest path algorithm functionality. The `DijkstraGraph` class extends a base graph structure to include methods for finding the shortest path between nodes, both in terms of the path sequence and total cost.

## Features

- Graph representation with nodes and weighted edges
- Dijkstra's algorithm implementation for shortest path finding
- Methods to retrieve:
  - The sequence of nodes along the shortest path (`shortestPathData`)
  - The total cost of the shortest path (`shortestPathCost`)
- Comprehensive test cases validating the implementation

## Implementation Details

### Key Components

1. **SearchNode Class**: A helper class that tracks path information during Dijkstra's algorithm execution, including:
   - Current node
   - Accumulated cost
   - Predecessor node in the path

2. **Core Methods**:
   - `computeShortestPath`: Internal method that implements Dijkstra's algorithm
   - `shortestPathData`: Returns the sequence of nodes in the shortest path
   - `shortestPathCost`: Returns the total weight of the shortest path

### Algorithm

The implementation follows Dijkstra's algorithm:
1. Initializes priority queue with the start node (cost = 0)
2. Processes nodes in order of increasing path cost
3. Updates costs for neighboring nodes when a cheaper path is found
4. Terminates when the target node is reached or all possibilities are exhausted

## Usage

### Creating a Graph

```java
DijkstraGraph<Character, Integer> graph = new DijkstraGraph<>();
graph.insertNode('A');
graph.insertNode('B');
graph.insertEdge('A', 'B', 5);
```

### Finding Shortest Path

```java
// Get path sequence
List<Character> path = graph.shortestPathData('A', 'B');

// Get path cost
double cost = graph.shortestPathCost('A', 'B');
```

## Test Cases

The implementation includes three test cases:

1. **test1**: Validates a basic shortest path calculation
2. **test2**: Tests a different start-end node pair
3. **test3**: Verifies proper exception handling when no path exists

## Dependencies

- Java Collections Framework
- JUnit 5 (for testing)

## Notes

- Implementation references pseudocode from lecture materials
- The graph uses generics to support various node and edge weight types
- Edge weights must extend `Number` to support numeric operations
