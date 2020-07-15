
## DISC-sigmod2021
we present a new incremental density-based clustering algorithm called DISC, which is optimized under the sliding window model.
DISC is capable of producing exactly the same clustering results as existing methods such as Incremental DBSCAN for streaming
data much more quickly without consuming too many computational resources.

## Contribution
We present an elaborate density-based clustering algorithm optimized under the sliding window model. The design of this algorithm is based on novel ideas defined in this paper for the minimal bonding cores of ex-cores and neo-cores. 
DISC can avoid a considerable amount of redundant work by checking the density-connectedness only for the minimal bonding cores.

We also present the MS-BFS strategy and the epoch-based probing for the R-tree index to further reduce the cost of checking density-connectedness.

Through an extensive evaluation carried out under various configurations, we have demonstrated that DISC is highly
effective especially when it is applied to finer-grained incremental clustering with the sliding window advancing frequently in a small stride. In most practical settings, DISC outperformed the state of the art (i.e., EXTRA-N and the Incremental DBSCAN) significantly.

This is example code for DISC, Incremental DBSCAN, and Extra-N
