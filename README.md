Database systems usually have many parameters that must be configured by database administrators and users. One of the database systems - RocksDB achieves fast data writing performance using a log-structured merged tree. This database has many parameters associated with write and space amplifications. Write amplification degrades the database performance, while space amplification leads to an increased storage space owing to the storage of unwanted data. These two amplicifations are trade-off. Previously, it was proven that significant performance improvements can be achieved by tuning the database parameters. However, tuning the hundreds of parameters is a laborious task owing to the large number of potential configuration combinations. To address this problem, we applied deep neural network to predict the performance of a target workload and used genetic algorithm to generate the best configuration. We used 5 statastical numbers to represent workloads to decrease dimensions of huge internal metrics, and applied Mahalanobis distance for workload mapping. We tuned 4 external metrics(TIME, RATE, WAF, SA) at the same time with our novel score function which is uesd in genetic algorithm and successfully found the optimal solution for target workloads.

