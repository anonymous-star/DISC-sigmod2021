# DISC: Density-Based Incremental Clustering by Striding over Streaming Data
we present a new incremental density-based clustering algorithm called DISC, which is optimized under the sliding window model.
DISC is capable of producing exactly the same clustering results as existing methods such as Incremental DBSCAN for streaming
data much more quickly without consuming too many computational resources.

## Explanation 

`DBSCANpack.jar`

There are three packages and one main file ( EvaluationSample.java ) in the DBSCANpack.jar.
In DBSCANpack package, there are source codes for DBSCAN, DISC, Incremental DBSCAN, and Extra-N all. 
In Rtree.BasicRtree package, there are source codes for Rtree
In Rtree.EpochBasedRtree package, there are source codes for the Epoch_Based_Probe method.

`Dataset`

Sample datasets for GeoLife, COVID19, IRIS are located in the Dataset folder. 
We do not upload DTG














