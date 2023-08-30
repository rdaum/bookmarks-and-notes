# bookmarks-and-notes

A place to put things people show me and I come across, since I keep losing/tangling mental threads. 
Mostly links to papers for now.

### db architecture / internals 

  * "An Empirical Evaluation of In-Memory Multi-Version Concurrency Control"; https://db.cs.cmu.edu/papers/2017/p781-wu.pdf ; A great overview of MVCC implementation techniques including a 
     performance comparison of different approaches across 4 axis (protocol/logic, storage model, garbage collection, and index mgmt)
  * "Scalable and Robust Snapshot Isolation for High-Performance Storage Engines"; https://www.vldb.org/pvldb/vol16/p1426-alhomssi.pdf
  * "Virtual-Memory Assisted Buffer Management"; https://www.cs.cit.tum.de/fileadmin/w00cfj/dis/_my_direct_uploads/vmcache.pdf
  * "Umbra: A Disk-Based System with In-Memory Performance" ; https://db.in.tum.de/~freitag/papers/p29-neumann-cidr20.pdf

### data structures 
  
#### Adaptive Radix Trees
  * "The Adaptive Radix Tree: ARTful Indexing for Main-Memory Databases"; https://db.in.tum.de/~leis/papers/ART.pdf
  * "Persistent Adaptive Radix Trees: Efficient Fine-Grained Updates to
    Immutable Data" ; https://ankurdave.com/dl/part-tr.pdf
  * "Parallelizing Approximate Search on Adaptive Radix Trees"; https://ceur-ws.org/Vol-2646/16-paper.pdf ; (2016) "We propose a parallel approximate search in the ART on CPU and GPU to optimize the throughput of queries and speed up applications that depends on these algorithms."
  * "The ART of Practical Synchronization" ; https://db.in.tum.de/~leis/papers/artsync.pdf ; Optimistic lock coupling for Adaptive Radix Trees
  * "Persistent Storage of Adaptive Radix Trees in DuckDB" ; https://duckdb.org/2022/07/27/art-storage.html ; How DuckDB came up with a scheme for paging on ARTs
  * "CuART - a CUDA-based, scalable Radix-Tree lookup and update engine"; https://dl.acm.org/doi/pdf/10.1145/3472456.3472511 / https://www.youtube.com/watch?v=ei_aNNNBNRA ; (2021) an optimized version of the Adaptive Radix Tree (ART) index structure for GPUs
  * "WORT: Write Optimal Radix Tree for Persistent Memory Storage Systems"; https://www.usenix.org/system/files/conference/fast17/fast17-lee.pdf ; (2017) write optimized radix trees for persistent storage

#### BTrees & Friends
  * "An Introduction to Bε-trees and Write-Optimization"; http://supertech.csail.mit.edu/papers/BenderFaJa15.pdf
  * "A GPU Multiversion B-Tree" ; https://dl.acm.org/doi/10.1145/3559009.3569681 / https://github.com/owensgroup/MVGpuBTree ; (2022) "We introduce a GPU B-Tree that supports snapshots and offers updates, point queries, and linearizable multipoint queries. The supported operations can be performed in a phase-concurrent, asynchronous, or fully-concurrent fashion."
  * "Stratified B-trees and Versioned Dictionaries." https://www.usenix.org/legacy/event/hotstorage11/tech/final_files/Twigg.pdf (2011) Alternative to CoW B-Trees for versioned dictionaries, with claims of greater space efficiency. Video talk: https://vimeo.com/26180574
 
## books

  * "Databases, Types & the Relational Model"; Chris Date's "3rd manifesto"; https://www.dcs.warwick.ac.uk/~hugh/TTM/DTATRM.pdf
  * "Foundations of Databases"; Alice Book; http://webdam.inria.fr/Alice/

## useful libraries / crates

  * https://github.com/Amanieu/hashbrown - Rust port of Google's high-performance SwissTable hash map, adapted to make it a drop-in replacement for Rust's standard HashMap and HashSet types.
  * https://github.com/m-ou-se/atomic-wait - Cross platform atomic wait and wake (aka futex) functionality. When one needs to build one's own customlocks..
