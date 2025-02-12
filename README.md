# Scalable-Database-Architecture-With-Database-Sharding 🚀
Database sharding is a technique used to distribute a large dataset across multiple databases (shards) to improve performance, scalability, and availability. Instead of storing all data in a single database, sharding splits the data into smaller, independent partitions (shards), each handled by a separate database server.

## Why Use Sharding?

- The database grows too large to fit on a single server.
- Read and write operations slow down due to high traffic.
- Scaling vertically (adding more CPU/RAM) becomes expensive.
- A globally distributed system is needed for faster access.

## Sharding Strategies

# A. Horizontal Sharding (Range-Based Sharding)

Data is split by range (e.g., customers A–M in one shard, N–Z in another).
Example: Orders table split based on order date (orders_2024_Q1, orders_2024_Q2).
✅ Pros: Simple to implement.
❌ Cons: Uneven distribution (some shards may have more data than others).

# B. Hash-Based Sharding 📂📂📂

A hash function distributes data evenly across shards.
Example: user_id % number_of_shards determines which shard to use.
✅ Pros: Prevents data skew (equal distribution).
❌ Cons: Harder to rebalance when adding/removing shards.

# C. Directory-Based Sharding

A lookup table stores which shard contains which data.
Example: A separate mapping table says user #123 is in shard_3.
✅ Pros: Flexible, supports dynamic growth.
❌ Cons: Adds complexity with an extra lookup.

# D. Geo-Based Sharding 

Data is sharded based on geographical regions.
Example: Customers in the USA stored in us_shard, Europe in eu_shard.
✅ Pros: Reduces latency by keeping data closer to users.
❌ Cons: Harder to scale across multiple regions.

