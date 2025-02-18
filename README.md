# k-means Project in RISC-V

This project involves the implementation of the **k-means clustering algorithm** in RISC-V assembly. The goal is to group a set of points in a two-dimensional (2D) space into **k clusters** based on the relative proximity of the points. The k-means algorithm is widely used in various fields, including computer vision, machine learning, cybersecurity, and astronomy.

## Project Description

The program takes the following inputs:
- A vector of 2D points (`points`), where each point is represented by a pair of coordinates (x, y).
- The number of points (`n_points`).
- The number of clusters (`k`).
- The maximum number of iterations (`L`).

The k-means algorithm runs iteratively, adjusting the clusters and centroids in each iteration. During execution, the clusters and centroids are visualized on a 32x32 LED matrix, with each cluster represented by a distinct color.

## Code Structure

The code is organized into several main functions, each implementing a different part of the algorithm:

1. **cleanScreen**: Clears the LED matrix, turning off all points.
2. **printClusters**: Displays the points on the LED matrix, assigning a specific color to each cluster.
3. **printCentroids**: Displays the centroids on the LED matrix, using a predefined color (e.g., black).
4. **calculateCentroids**: Computes the new centroids based on the current cluster assignments.
5. **manhattanDistance**: Calculates the Manhattan distance between two points.
6. **nearestCluster**: Determines the nearest centroid for a given point.
7. **randomCentroids**: Initializes the centroids with pseudo-random coordinates.
8. **calculateClusters**: Updates the cluster assignments for all points based on the nearest centroid.
9. **mainKMeans**: Executes the k-means algorithm, iterating until convergence or the maximum number of iterations is reached.

## How It Works

1. **Initialization**: The centroids are initialized with pseudo-random coordinates using the `randomCentroids` function.
2. **Cluster Assignment**: For each point, the nearest centroid is determined using the `nearestCluster` function, and the point is assigned to that cluster.
3. **Centroid Update**: The centroids are recalculated based on the current cluster assignments using the `calculateCentroids` function.
4. **Visualization**: The points and centroids are displayed on the LED matrix using the `printClusters` and `printCentroids` functions.
5. **Iteration**: Steps 2-4 are repeated until the centroids no longer change or the maximum number of iterations is reached.

## LED Matrix Visualization

The LED matrix is used to visualize the clusters and centroids:
- Each cluster is represented by a unique color (defined in the `colors` array).
- Centroids are displayed in black.
- The matrix is updated after each iteration to reflect the current state of the clusters and centroids.

## Example Inputs

The project includes several example inputs in the `.data` section, such as:
- A diagonal line of points.
- A cross-shaped set of points.
- A more complex distribution of points.

You can uncomment the desired input in the code to test the algorithm with different datasets.

## Running the Code

To run the code:
1. Open the project in the RISC-V simulator (e.g., Ripes).
2. Load the provided assembly file (`projetoiacgrupo33.s`).
3. Set up a 32x32 LED matrix in the I/O section of the simulator.
4. Run the program and observe the clustering process on the LED matrix.

## Dependencies

- **RISC-V Simulator**: The project is designed to run on a RISC-V 32-bit processor. We recommend using the Ripes simulator for testing and visualization.
- **LED Matrix**: A 32x32 LED matrix is used for visualizing the clusters and centroids. This can be configured in the simulator's I/O settings.
