# 6 The Cassandra Architecture

## Data Centers and Racks - 105

1. What is a _data center_?
2. What is a _rack_?


## Gossip and Failure Detection - 106

1. What is Cassandra's gossip protocol?
2. How offten the gossiper runs?
3. What are gossip protocols in general used for, and where?
4. What is the `Gossiper` class used for?
5. How the gossiper works? What messages each round of gossip requires?
6. What happens if the gossiper determines that another endpoint is dead?
7. What is accrual failure detection (AFD)? (what accrual means?)
8. What are two primary ideas of accrual failure detection?
9. What is the advantage of AFD when compared to a simple binary assessment?

## Snitches - 108

1. What is a job of the snitch? 
2. What is the role of snitch in a read opperation?
3. What is the default snitch?
4. What is _dynamic snithcing_? How it works? What is a similarity with gossip?
5. What is _badness threshold_?

## Rings and Tokens - 109

1. What is a _ring_?
2. How are ranges assigned to a node in a ring?
3. What is a _token_?

## Virtual Nodes - 110

1. Why did Cassandra introduces the concept of _virtual nodes_ (_vnodes_)? How the tokens and ranges were calculated before _virtual nodes_?
2. What is `num_tokens` property in the `cassandra.yaml` file used for?
3. Why vnodes speed up bootstrapping, decommissioning, and repairing a node?

## Partitioners - 111

1. What a _partitioner_ is used for?
2. Is it possible to plug your own implementation of a partitioner? How?

## Replication Strategies - 112

1. What is a _replica_?
2. What is a _replication factor_?
3. How the first replica?
4. What is _replication strategy_?
5. What are two primary implementations of `AbstractReplicationStrategy`? How they place replicas?

##  Consistency Levels - 113

1. When is the consistency level specified?
2. What does consistency level specify for read and write?
3. What are available consistency levels?
4. Which consistency levels are considered weak and which are considered strong?
5. What is the difference between consistency level and replication factor?

## Queries and Coordinator Nodes - 114

1. What is _coordinator node_? What does it do?

## Memtables, SSTables, and Commit Logs - 115

1. What is the purpose of _commit log_? When a commit log is read from?
2. What is a _memtable_? In which memory memtables are (mostly) stored and why?
3. When are memtables flushed to disk?
4. What happens with commit log when a memtable is flushed?
5. What is a _SSTable_?
6. Explain properties of SSTable (immutability, sequetial writes).
7. On read, where does Cassandra read from?

## Caching - 117

1. Which forms of caching does Cassandra provide? Explain each one.
2. Which ones are enabled by default?

## Hinted Handoff - 118, [docs](https://docs.datastax.com/en/cassandra/3.0/cassandra/operations/opsRepairNodesHintedHandoff.html)

1. What is a _hinted handoff_?
2. Do hints count as writes for the purposes of consistency level?

## Lightweight Transactions and Paxos - 118, [docs](https://docs.datastax.com/en/cassandra/3.0/cassandra/dml/dmlLtwtTransactions.html)

1. What is _linearizable consistency_?
2. What is Paxos?
3. Explain LWT and Paxos :)

## Tombstones - 120

1. What is a _tombstone_?
2. What is `GCGraceSeconds` setting and what is the default value for it?

## Bloom Filters - 120

1. What is a _bloom filter_?
2. How bloom filter works (on a high level)?

## Compaction - 121

1. What is compaction, why it occurs, and what happens during compaction?
2. Which compaction strategies are available with Cassandra?

## Anty-Entropy, Repair, and Merkle Trees - 122

1. What is an _anti-entropy protocol_ and how it works?
2. How are replica synchronized (two modes)?
3. What is a _read repair_ and how it works?
4. What is an _anti-entropy repair_ (a.k.a. manual repair) and how it works?
5. What is a Merkle tree?

## Staged Even-Driven Architecture (SEDA) - 124

1. What is SEDA?
2. What are the stages in Cassandra?

## Managers and Services - 125

1. What is `CassandraDaemon` interface used for? What opperations does it support?
2. What is `EmbeddedCassadnraService` class used for?
3. What is `ColumnFamilyStore` class used for?
4. What is `StorageService` class used for?
5. What is `StorageProxy` class used for?
6. What is `MessageService` class used for?
7. What is _streaming_? Which protocol does it use?
8. What is CQL Native Protocol?

## System Keyspaces

1. Describe following System keyspaces:
  1. system.local and system.peers
  2. system.range_xfers and system.available_ranges
  3. system_schema.keyspaces, system_schema.tables, and system_schema.columns
  4. systemmaterialized_views_builds_in_progress, system.built_materialized_views, and syste_schema.materialized_views
  5. system_schema.types, system_schema.triggers, system_schema.functions, system_schema.aggregates
  6. system.paxos, system.batchlog
  7. system.size_estimates 
