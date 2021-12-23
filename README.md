# PathPlanningAlgorithms JPS (JumpPoint Search)

## Description

In the file `JPS_upg.ipynb` implements two heuristic search algorithms for 8-connected uniform-cost greed:
- A*, in which it is allowed to cut corners (see figure), with a diagonal heuristic
- JPS with a diagonal heuristic, where it is also assumed that the agent can cut corners.

This project uses

- Jupyter python notebook

## Installing

Download current repository to your local machine. Use

```bash
git clone https://github.com/Classman-wand/JPS/
```

The project requires python modules:

- PIL
- numpy
- matplotlib
- math
- heapq
- queue

To install them use bash command

```bash
pip install module
```
or insert into ipynb cell
```
!pip install module
```
## Input and output

### Input file

- Input files of our algorithm: two files with extensions `.map` and `.map.scen` in the [movingai](https://movingai.com/benchmarks/formats.html) format.


You can see an example of input data in the folder `maps`. [Sample](./maps/lt_house.map). In case of incorrect data, there may be undefined behavior.

### Output file

- Tag `root`. It describes the parameters.
  - `time` - algorithm running time.
  - `countofedges` - number of edges created.
  - `pathfound` - the tag that describes whether a path is found.
  - `distance` - length of the path found.
  - `path` - describes points of the path.
  - `timefirst` - it is only for RRT*, algorithm running time, time spent finding the first path.
  - `countofedgesfirst` - it is only for RRT*, count of edges spent finding the first path.
  - `distancefirst` - it is only for RRT*, distance finding the first path.
  - `pathfirst` - it is only for RRT*, describes points of the first path.



### Map ht_chantry

- Algorithm: A*
![vis](./Images/ht_chantry_A*.png)

- Algorithm: JPS
![vis](./Images/ht_chantry_JPS.png)

### Map ht_store

- Algorithm: A*
![vis](./Images/ht_store_A*.png)

- Algorithm: JPS
![vis](./Images/ht_store_JPS.png)

### Map lt_house

- Algorithm: A*
![vis](./Images/lt_house_A*.png)

- Algorithm: JPS
![vis](./Images/lt_house_JPS.png)


## Sources

- Daniel Harabor, Alban Grastien, [Online Graph Pruning for Pathfinding on Grid Maps](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwij6YPcy_n0AhXksIsKHQLvCl4QFnoECAgQAQ&url=https%3A%2F%2Fwww.aaai.org%2Focs%2Findex.php%2FAAAI%2FAAAI11%2Fpaper%2Fdownload%2F3761%2F4007&usg=AOvVaw3sWq3vcrlKtPCuZeefIdd-). NICTA and The Australian National University
- Nathan Sturtevant, [Moving AI Lab](https://movingai.com)
- Yakovlev Konstantin, Course on Methods and Algorithms for Heuristic Search. St. Petersburg State University
