# DISC: Density-Based Incremental Clustering by Striding over Streaming Data
We present a new incremental density-based clustering algorithm called DISC, which is optimized under the sliding window model.
DISC is capable of producing exactly the same clustering results as existing methods such as Incremental DBSCAN for streaming
data much more quickly without consuming too many computational resources.

## Datasets 
Samples for the public datasets (GeoLife, COVID19, IRIS) are in the [Datasets](https://github.com/anonymous-star/DISC-sigmod2021/blob/master/Datasets)
 folder. 
For the privay issue, we do not upload the DTG dataset. 

## RUN ALGORITHMS (DISC, DBSCAN, Incremental DBSCAN, Extra-N)
We provide the runnable jar([EvaluationSample.jar](https://github.com/anonymous-star/DISC-sigmod2021/blob/master/EvaluationSample.jar)) to simply test the performance of each algorithm shown in the paper. *It is compiled under javaSE-1.8.    
EvaluationSample.jar measures the elapsed time taken to update clusters when the sliding window advanced by a single stride and returns the average elapsed time of `X` sequential runs. 


### Running EvaluationSample.jar
```
java -jar EvaluationSample.jar [Path] [Datasets] [Algorithm] [MinPts] [Eps] [Window] [Stride] [X]
```
`Path` = Path to the folder of datasets (ex ~/home/Datasets)   
`Datasets` = 0 | 1 | 2    (0: GeoLife, 1: COVID19, 2: IRIS)   
`Algorithm` = DBSCAN | EXTRAN | DISC | INCDBSCAN | ALL    
`MinPts` = Integer value for MinPts   
`Eps` = Double value for Epsilon    
`Window` = Integer value for the window size   
`Stride` = Integer value for the stride size    
`X` = Integer value for sequential runs

>Example
```
ex) java -jar EvaluationSample.jar ~/path/Datasets 1 ALL 5 1.0 15000 150 5
```

>Sample Output

![Sample](https://user-images.githubusercontent.com/68207451/87643027-49259900-c785-11ea-9463-33f8a9a85c3e.png)






