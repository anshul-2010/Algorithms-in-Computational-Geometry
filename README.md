# Algorithms-in-Computational-Geometry
This project delves into the exciting realm of dynamic Voronoi diagrams, extending the traditional concept to handle points continuously moving within a 2D plane. Here, we explore how Voronoi diagrams adapt and evolve in response to these dynamic movements, offering novel perspectives for various applications.

## Project Goals
* Investigate the theoretical implications of dynamic point movement on fundamental geometric structures like Voronoi diagrams.
* Implement a dynamic Voronoi diagram using the efficient parabolic front approach within Fortune's algorithm.
* Develop interactive tools for visualizing and understanding the behavior of dynamic Voronoi diagrams.
* Explore potential applications of dynamic Voronoi diagrams in fields like robotics (obtacle avoidance in dynamic environments), sensor networks (analyzing and optimizing sensor placement), and protein analysis (studying binding sites and protein-ligand interactions).

## Traditional vs. Dynamic Voronoi Diagrams
Conventional Voronoi diagrams partition a space into distinct regions based on their proximity to a set of static points. This project disrupts this notion by introducing continuously moving points. Here, the Voronoi diagram needs to be a dynamic representation that constantly adjusts to the evolving spatial relationships between the points.

## Methodology
- `Fortune's Algorithm with Parabolic Front`: We leverage the efficiency of Fortune's algorithm, a well-established algorithm for constructing Voronoi diagrams. However, to handle moving points, we incorporate the parabolic front technique. This technique efficiently tracks the evolving boundaries (represented by parabolas) of the Voronoi diagram as points move.
- `Dynamic Point Movement`: Points are modeled as objects with attributes like position, color, and movement direction. These points continuously update their positions within a defined 2D space, introducing randomness for natural-looking dynamics. Boundary conditions are implemented to ensure points stay within the designated canvas.
- `Visualization and Animation`: Libraries like Matplotlib and Tkinter are employed to create informative visualizations and animations.
  - Matplotlib allows us to generate high-quality static and animated visualizations of the Voronoi diagram, enabling us to observe how the diagram changes over time.
  - Tkinter is used to create a user-friendly graphical user interface (GUI) where users can interactively create and visualize Voronoi diagrams.
 
## Code Structure
The codebase is organized into several well-defined modules, promoting readability and maintainability:
* `Core Algorithms`: This module implements Fortune's algorithm with the parabolic front approach for dynamic Voronoi diagram construction. Here, you'll find functions for handling site events (when the sweep line encounters a new point), circle events (when three consecutive points form a circle), and updating the beach line data structure (which efficiently stores and manages the parabolic arcs).
* `Data Structures`: This module defines classes representing the essential building blocks for the algorithm:
  - `Point`: Represents a two-dimensional point with x and y coordinates.
  - Event: Captures both site events and circle events, crucial for driving the dynamic updates to the Voronoi diagram.
  - `Arc`: Represents parabolic arcs within the beach line, a key structure for constructing the Voronoi diagram. It stores information about the associated point, neighboring arcs, and the corresponding Voronoi edges (segments).
  - `Segment`: Represents line segments or edges in the evolving Voronoi diagram. It includes attributes for start and end points, and a flag indicating whether the segment is complete.
  - `PriorityQueue`: Implements a priority queue using a min-heap structure to efficiently manage site and circle events based on their x-coordinates along the sweep line.
