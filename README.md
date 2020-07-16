# DISC: Density-Based Incremental Clustering by Striding over Streaming Data
We present a new incremental density-based clustering algorithm called DISC, which is optimized under the sliding window model.
DISC is capable of producing exactly the same clustering results as existing methods such as Incremental DBSCAN for streaming
data much more quickly without consuming too many computational resources.

### Datasets 
Sample subset of the public datasets (GeoLife, COVID19, IRIS) are located in the [Datasets](https://github.com/anonymous-star/DISC-sigmod2021/blob/master/Datasets)
 folder. 
For the privay issue, We do not upload the DTG dataset. 

## Description
We provide sources (`src` folder) of all clustering algorithms used in the paper and the executable jar (`EvaluationSample.jar`) which is a sample program to simply test the algorithms. 

### Running EvaluationSample.jar
It measures the elapsed time taken to update clusters when the sliding window advanced by a single stride.
It returns the average elapsed time of five runs.
```
java EvaluationSample.jar [Path] [Datasets] [Algorithm] [MinPts] [Eps] [|Window|] [|Stride|] 
```
`Path` = Path to dataset folder  ex) ~/home/Datasets   
`Datasets` = 0 | 1 | 2    ## 0: GeoLife, 1: COVID19, 2: IRIS   
`Algorithm` = DBSCAN | EXTRAN | DISC | INCDBSCAN | ALL    
`MinPts` = Integer value for MinPts   
`Eps` = Double value for epsilon    
`|Window|` = Integer value for window size   
`|Stride|` = Integer value for stride size    

```
ex) java EvaluationSample.jar ~/home/Datasets 0 DBSCAN 20 0.005 15000 1500 
```

### src
There are three packages and one main file (EvaluationSample.java) in the [DBSCANpack.jar](https://github.com/anonymous-star/DISC-sigmod2021/blob/master/DBSCANpack.jar).
In DBSCANpack package, there are source codes for DBSCAN, DISC, Incremental DBSCAN, and Extra-N all. 
In Rtree.BasicRtree package, there are source codes for basic Rtree
In Rtree.EpochBasedRtree package, there are source codes for  Rtree with the Epoch_Based_Probe method .


#### How to compile

















