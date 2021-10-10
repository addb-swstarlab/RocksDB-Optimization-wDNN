Database systems typically have a large number of knobs that must be configured by database administrators and users to achieve high performance. RocksDB achieves fast data writing performance using a log-structured merge-tree. This database contains many knobs related to write and space amplification, which are important performance indicators in RocksDB. Write amplification degrades the database performance, whereas space amplification increases storage space owing to the storage of redundant data. Previously, it was proved that significant performance improvements could be achieved by tuning the database knobs. However, tuning multiple knobs simultaneously is a laborious task due to the large number of potential configuration combinations and trade-offs.
To address this problem, we built a system for RocksDB tuning. First, we generated a valuable RocksDB data repository for data analysis and tuning. The RocksDB data repository includes 20,000 random configurations for 16 different workloads, and the total number of pairs of data is 320,000. To find the workload that is most similar to a target workload, we created a new representation for workloads. We then applied the Mahalanobis distance to the data repository and a target workload to create a combined workload that is as close to the original target workload as possible and regarded the combined workload as the target workload. Subsequently, we trained a deep neural network model with the combined workload and used it as the fitness function of a genetic algorithm. Finally, we applied the genetic algorithm to find the best solution for the original target workload. The experimental results demonstrated that the proposed system achieved a significant performance improvement for various target workloads. Moreover, we conducted several experiments for performance comparison, including metrics pruning, knob pruning, workload combining, varying weights, and different hardware environments. 



