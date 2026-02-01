**Core Mechanism:** Out-of-core learning is a technique used when a dataset is **too large to fit into a computer's main memory (RAM)**. Instead of loading the entire dataset at once, the algorithm processes the data in small chunks (batches) from the disk (Hard Drive/SSD), updates the model, and then discards that chunk to load the next one.
**Key Properties:**

- **Incremental Learning:** The model must support "partial fits," meaning it can update its internal weights without needing to see the previous data again.
- **Data Streaming:** Utilizes disk-reading generators or iterators to feed data.    
- **Scalability:** Allows training on terabytes of data using a machine with only 8GB or 16GB of RAM.
- **Performance:** The bottleneck is usually disk I/O (reading speed) rather than CPU/GPU speed.