# PathPlanningAlgorithms JPS (JumpPoint Search)

## Description

In the file `JPS_upg.ipynb` implements two heuristic search algorithms:
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
or insertinto ipynb cell
```
!pip install module
```
## Input and output

### Input file

- Input files of our algorithm: two files with extensions `.map` and `.map.scen` in the [movingai](https://movingai.com/benchmarks/formats.html) format.
- Example of input file `.map`
  - Tag `map`. It describes the map.
    - `height` - the height of the field. A positive number.
    - `width` - the width of the field. A positive number.
    - `startx` - the start coordinate x. A number from `0` to `width - 1`.
    - `starty` - the start coordinate y. A number from `0` to `height - 1`.
    - `finishx` - the finish coordinate x. A number from `0` to `width - 1`.
    - `finishy` - the finish coordinate y. A number from `0` to `height - 1`.
    - Tag `grid` describes your map, where each line is separated by a `line` tag. `0` is free cell, `1` is obstruction.
  - Tag `algorithm` describes the algrithm options.
    - `searchtype` - the type of the search. Arguments are `rrt` or `rrtstar`. RRT and RRT* algorithm, respectively.
    - `numberofiterations` - number of iterations of the algorithm. In the case of RRT, if a path is found, the construction of the tree stops. In the case of RRT* algorithm will be improve path length. If you do not specify this tag, the default is set to 100000.
    - `stepsize` - maximum edge size in a tree. If you do not specify this tag, the default is set to 3. The value must be greater or equal than 1.
    - `eps` - error area the finish point. If you do not specify this tag, the default is set to 3. The value must be greater or equal than 1.
    - `gamma` - constant for RRT*, see RRT* description for details.
  - Tag `log` - specified output options. This is optional. If there are not the tag, the output file will be create in the same name and directory with suffix _log.
    - `path` - path to output file(with the name of file).

You can see an example of input data in the folder `tests`. [Sample](https://github.com/Ch0p1k3/PathPlanningAlgorithms-RRT-RRTstar-/blob/main/tests/sample/example.xml). In case of incorrect data, there may be undefined behavior.

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

[Example of output data](https://github.com/Ch0p1k3/PathPlanningAlgorithms-RRT-RRTstar-/blob/main/tests/sample/example_log.xml).


### Launch with visualizer

- `-v`

RRT
![vis](https://github.com/Classman-wand/JPS/images/ht_chantry_A*.png)
![vis](https://github.com/Classman-wand/JPS/images/ht_chantry_JPS.png)


## Sources

- LaValle, Steven M., Rapidly-exploring random trees: A new tool for path planning. Technical Report. Computer Science Department, Iowa State University  [**URL**](http://msl.cs.uiuc.edu/~lavalle/papers/Lav98c.pdf)

- LaValle, Steven M.; Kuffner Jr., James J., Randomized Kinodynamic Planning. The International Journal of Robotics Research (IJRR), [**URL**](http://msl.cs.uiuc.edu/~lavalle/papers/LavKuf01b.pdf)
		
- Karaman Sertac, Frazzoli Emilio, Incremental Sampling-based Algorithms for Optimal Motion Planning, [**URL**](https://arxiv.org/pdf/1005.0416.pdf)

- Karaman Sertac, Frazzoli Emilio, Sampling-based Algorithms for Optimal Motion Planning, [**URL**](https://journals.sagepub.com/doi/pdf/10.1177/0278364911406761?casa_token=ru3w0CN-S1kAAAAA:PZXGaHXATpK2HATSCe6dzIKmdD9Sw5SpMgfY5nvRT3_k2u6LIeMh_keR20m6EYjYQuQoaDzhCteg)

- Iram Noreen, Amna Khan, Zulfiqar Habib, Optimal Path Planning using RRT* based, [**URL**](https://pdfs.semanticscholar.org/9c35/2fec7a86c875eec17fc054106414b6914b7d.pdf)

- Sturtevant, N., Transactions on Computational Intelligence and AI in Games, Benchmarks for Grid-Based Pathfinding, vol. 4, num. 2, pp. 144-148
