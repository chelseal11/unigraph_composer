# Unigraph Composition Tool

<Intro on unigraphs>
<something about Tyshkevich's theorem>
<her wiki page: https://en.wikipedia.org/wiki/Regina_Tyshkevich>
terminologies are based on <link to her paper>
<link to her paper>

A web-based tool for computing compositions of indecomposable unigraphs through their degree sequences. This tool allows researchers and students to explore related to unigraphs by creating an unlimited number of unigraphs, as previous composition results can be iteratively composed with other graphs to generate new structures.

## Table of Contents
- [Mathematical Background](#mathematical-background)
- [Features](#features)
- [Supported Graph Types](#supported-graph-types)
- [Available Versions of a Unigraph](#available-versions-of-a-unigraph)
- [How to Use](#how-to-use)
- [Examples](#examples)
- [Technical Details](#technical-details)
- [Installation](#installation)
- [Use Cases](#use-cases)

## Mathematical Background

This tool is designed for research in graph theory, specifically:
- **Graph Composition**: Adding edges between every vertex in Graph 1 and partition A in Graph 2.
- **Inverse**: A version of the graph where all of the vertices in partiion B are adjacent so that B becomes the new complete graph A and all of the vertices in partition A have their edges removed so that they become stable set B.
- **Complement**: A version of the graph where all edges are reversed so that if an edge wasn't present in the standard version, it exists in the complement, and vice versa.

## Features

- **Complete Graph Type Coverage**: Support for all types of indecomposable unigraphs discovered in Tyschevich's research, including cycles, complete graphs, and specialized graph families
- **Graph Operations**: Calculate the degree sequence for the inverse, complement and inverse of the complement of a graph.
- **Real-time Degree Sequence Display**: See degree sequences update as you modify parameters
- **Interactive Composition**: Compute the degree sequence of the composition of two graphs
- **Previous Result Integration**: Use the result of a previous composition as input for new calculations

## Supported Graph Types

### Non-Split Graphs
- **C₅**: 5-cycle graph
- **mK₂**: m disjoint edges (m ≥ 2)
- **U2(m, l)**: Specialized unigraph with parameters m ≥ 1, l ≥ 2
- **U3(m)**: Specialized unigraph with parameter m ≥ 1
- **Previous Result**: Use the output of a previous composition as input

### Split Graphs
- **Single-vertex Graph (SVG)**: Configurable to partition A or B
- **S(p, q)**: Graph family with parameters p ≥ 1, q ≥ 2
- **S2(p1, q1, ..., pm, qm)**: Multi-parameter graph family where m ≥ 2 and p1 > p2 > ... > pm
- **S3(p, q1, q2)**: Three-parameter graph family (p ≥ 1, q1 ≥ 2, q2 ≥ 1)
- **S4(p, q)**: Two-parameter graph family (p ≥ 1, q ≥ 1)

## Available Versions of a Unigraph

1. **Standard**: Use the graph as-is
2. **Inverse**: Calculate the inverse
3. **Complement**: Calculate the complement
4. **Complement of Inverse**: Calculate the complement of the inverse

## How to Use

### Getting Started
1. Open `https://chelseal11.github.io/unigraph_composer/` in a web browser
2. Configure Graph 1 by selecting a graph type and entering required parameters
3. Configure Graph 2 similarly
4. Choose a version of each graph (standard is default)
5. Click "Compute Composition" to see the result

### Graph Configuration
- **Select Graph Type**: Choose from the dropdown menu
- **Enter Parameters**: Fill in the required numerical parameters based on the selected graph type
- **Choose Version**: Select a version of the graph before composition
- **Monitor Degree Sequence**: The degree sequence updates automatically as you change parameters

### Special Cases

#### S2 Graph Configuration
The S2 graph type requires dynamic input:
1. Enter the value for `m` (number of parameter pairs)
2. Additional input fields for p₁, p₂, ..., pₘ and q₁, q₂, ..., qₘ will appear
3. Ensure p₁ > p₂ > ... > pₘ (descending order)

#### Single-vertex Graph (SVG)
- Choose whether the vertex belongs to partition A or B
- This affects how the graph participates in compositions

#### Using Previous Results
- After computing a composition, the result becomes available as "Previous Result"
- Select this option to use the computed result as input for new compositions
- Useful for chaining multiple composition operations

## Examples

### Basic Composition
1. **Graph 1**: Select C₅ (5-cycle)
2. **Graph 2**: Select SVG with partition A
3. **Result**: Degree sequence showing the composition

### Complex Chain
1. Start with U2(2,3) ∘ S(1,2)
2. Use the result as "Previous Result" for Graph 1
3. Compose with S3(1,2,1) to create an even more complex unigraph

## Technical Details

### Degree Sequence Format
Degree sequences are displayed in the format: `degree^count, degree^count, ...`
- For split graphs: `A_degrees; B_degrees`
- Example: `3^2, 1^4; 2^3` means partition A has 2 vertices of degree 3 and 4 vertices of degree 1, while partition B has 3 vertices of degree 2

### Composition Algorithm
The tool implements unigraph composition by:
1. Computing degree sequences for each input graph
2. Calculating the degree sequence for the alternate version if necessary
3. Performing the composition operation
4. Displaying the resulting degree sequence

### Validation
- Input validation ensures parameters meet minimum requirements
- Real-time feedback via alerts for invalid configurations
- Automatic parameter validation before composition

## Installation

### Local Development
1. Clone or download the repository
   ```bash
   git clone https://github.com/chelseal11/unigraph_composer.git
   cd unigraph_composer
   ```
2. Open `index.html` in your IDE of choice and make any changes.
3. Run a local server:
   ```bash
   python3 -m http.server 8000
   ```
4. Open `localhost:8000` in your browser

### Browser Compatibility
- Works in all modern browsers (Chrome, Firefox, Safari, Edge)
- Requires JavaScript to be enabled
- No server-side components needed

## Use Cases

- **Research**: Explore degree sequences of graphs and their compositions in academic research
- **Education**: Demonstrate graph theory concepts in classroom settings
- **Experimentation**: Test hypotheses about graph properties and compositions
- **Verification**: Confirm theoretical results with concrete examples
- **Create Unigraphs**: Create larger, unique unigraphs from any combination of indecomposable unigraphs.
