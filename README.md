# Graph Implementation

This repository contains the implementation of various graph methods and algorithms using a custom `Graph` class in Python. The class and associated methods are designed to represent directed graphs with weighted edges and provide fundamental functionalities.

## Table of Contents

- [Classes](#classes)
  - [Graph Class](#graph-class)
  - [Controller Class](#controller-class)
- [Graph Algorithms](#graph-algorithms)
  - [Breadth-First Search (BFS)](#breadth-first-search-bfs)
  - [Lowest Cost Walk](#lowest-cost-walk)
  - [Prim's Algorithm](#prims-algorithm)
  - [Approximate TSP (Hamiltonian Cycle)](#approximate-tsp-hamiltonian-cycle)

## Classes

### Graph Class

The `Graph` class provides a set of methods to work with directed graphs. Here are some of the main functionalities:

- **Initialization**:
  - `Graph(vertices_counter=0, copies=None)` initializes the graph with a specified number of vertices.

- **Vertex and Edge Management**:
  - `adder_of_vertex_into_graph(v)` adds a vertex to the graph.
  - `remover_of_vertex_from_graph(v)` removes a vertex and its associated edges.
  - `adder_of_edge_to_graph(start_node, end_node, cost)` adds an edge with a cost between two vertices.
  - `remover_of_edge_from_graph(start_node, end_node)` removes an edge between two vertices.

- **Graph Properties**:
  - `getter_for_all_vertices()` returns the set of all vertices.
  - `getter_number_of_edges()` and `getter_number_of_vertices()` return the number of edges and vertices, respectively.
  - `has_self_loop(node)` checks if a vertex has a self-loop.
  - `getter_of_outbound_neighbours(v)` returns the outbound neighbors of a vertex.
  
- **Graph Copy**:
  - `getter_of_copy_of_graph()` returns a deep copy of the graph.
  - `set_copy_of_graph()` sets the current graph to a previously saved copy.

### Controller Class

The `Controller` class provides methods to handle graph input/output, random graph generation, and to execute specific graph algorithms.

- **File Operations**:
  - `read_graph_from_file(filename)` reads a graph from a file.
  - `write_graph_to_file(filename)` writes the current graph to a file.

- **Random Graph Generation**:
  - `generate_random_graph(nr_of_vertices, nr_of_edges)` generates a random graph with the specified number of vertices and edges.

## Graph Algorithms

### Breadth-First Search (BFS)

The `forward_bfs(start_node, end_node)` method in the `Controller` class performs a forward breadth-first search to find the shortest path between two nodes in a directed graph.

### Lowest Cost Walk

The `lowest_cost_walk(start_vertex, end_vertex)` method computes the lowest cost walk between two vertices in the graph, considering all possible paths and checking for negative cost cycles.

### Prim's Algorithm

The `prim_algorithm(start)` method finds the minimum spanning tree (MST) of the graph starting from a given vertex using Prim's Algorithm.

### Approximate TSP (Hamiltonian Cycle)

The algorithm implemented here provides an approximate solution to the Traveling Salesman Problem (TSP) by finding a Hamiltonian cycle of low cost in an undirected graph with weighted edges. The heuristic used is as follows:

- **Heuristic**: Starting from a given vertex, repeatedly choose the edge with the minimum cost that does not close a cycle of length less than the total number of vertices (`n`), until all vertices are visited.
  
- **Objective**: To find a Hamiltonian cycle (a cycle that visits every vertex exactly once and returns to the starting point) with a low total cost, providing an efficient approximation for the TSP.
