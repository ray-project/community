# SIG Graph Algorithms

## Objective

Graphs are becoming increasingly popular for data analysis due to their ability to efficiently represent non-structured, high-dimensional data in non-Euclidean space. As a result, many Ray users and Ray Ecosystem library authors have indicated interest in: 

* Scaling out their graph algorithms to multiple nodes;
* Enabling large-scale distributed graph training, serving, and preprocessing; 
* Training graph neural networks (GNN) on large graph databases;
* ...and much more.

To that end, the purpose of this special interest group will be to define and maintain a collection of well-established APIs and data structures that implement novel, graph-related functionality not previously available in Ray or its supplemental libraries (Train, Tune, Serve, Datasets, etc.).

## Scope

This group supports, prioritizes, and maintains graph-related features within the open-source Ray repository. This additional graph-related functionality fits the following criteria:

* The functionality is generic enough to be included in Ray itself, rather than in a supplemental or framework-specific higher-level library (ex: [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/en/latest/)).
* The functionality conforms to an established API pattern in Ray or its affiliate libraries (ex: Train, Serve, Datasets).
* The functionality must include unit tests, and the functionality must evolve as Ray evolves.
* The new functionality conforms to the code and documentation standards defined by the group. These policies are detailed in the Ray project's [contributor guide]().
* The functionality is useful for a large number of users (e.g., an implenentation used in widely cited paper, or a utility with broad applicability)

The SIG Graph Algorithms group is responsible for reviewing and scoping out any new graph-related additions to Ray Train, Ray Datasets, and Ray Serve, including evaluating designs and implementations.

## Membership

Anyone with an interest in helping extend the Ray open-source project with new types of graph-related functionality is welcome to join the special interest group. Maintainer status for the repository will be conferred by consensus of the existing members. Archives of the SIG's meeting minutes are publicly accessible, as a GitHub issue referenced in the `graph-algorithms` folder.

## Resources

* SIG Graph Algorithms mailing list (?)
* Features added by SIG Graph Algorithms
* SIG design docs 

## Contacts

* Project leads: ???
* Ray OSS technical contact: @amogkam, @richardliaw
* Ray OSS product contact: @dynamicwebpaige

## Code of Conduct

As with all forums and spaces related to the open-source Ray developer community, this special interest group is subject to the [Ray Community Code of Conduct](https://github.com/ray-project/community/blob/main/CODE_OF_CONDUCT.md).
