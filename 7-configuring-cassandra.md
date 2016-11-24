# Cassandra Cluster Manager

1. `ccm` - (https://github.com/pcmanus/ccm)

# Creating a Cluster - 132

1. What are the key values (in cassandra.yaml) in configuring a cluster? What is the requirement for the values in respect to all nodes in a cluster?
2. ccm commands:
  - `ccm create -v 3.0.0 -n 3 my_cluster --vnodes`
  - `ccm list`
  - `ccm status`
  - `ccm start`
  - `ccm node1 status`
  - `ccm node1 ring`

# Seed Nodes - 135

1. What is the purpose of a _seed node_?
2. What is _(auto) bootstrapping_?
3. What is the purpose of `SeedProvider` interface? What is the default implementation?

# Partitioners

1. What is the purpose of the partitioner?
2. What is the default partitioner?
3. How Murmur3Partitioner generates tokens? What are the advantages and disadvantages?
4. How RandomPartitioner works? Why it was replaced by Murmu3Partitioner as the default one?
5. What is the advantage of OrderPerservingPartitioner? Is it more efficient for range queries? Why? What is the disadvantage of this partitioner?
6. How ByteOrderedPartitioner works?


# Snithes - 138

1. `endpoint_snitch`
2. What is `SimpleSnitch`? What replication strategy is used with this snitch?
3. What is a `ProperyFileSnitch`? Where does it read topology information from? Main advantages and disadvantages?
4. What is a `GossipingPropertyFileSnitch`? Where does it read the topology information from? Does it use `cassandra-topology.properties` file? Why (i don't know :))?
5. How RackInferringSnitch works?
6. What cloud snitches exist?
7. What is the purpose of DynamicEndpointSnitch? What are the configuration properties for it?

# Node Configuration - 140, [docs guide](http://docs.datastax.com/en/cassandra/3.0/cassandra/configuration/configCassandra_yaml.html)

## Tokens and VNodes

1. What is `num_tokens` property from cassandra.yaml?

## Network Interfaces 142

1. explain: `listen_interface`, `listen_address`, `storage_port`, `ssl_storage_port` Thrift API vs _native transport_, `start_native_transport`, `native_transport_port`, `rpc_port`, `rpc_keepalive`.

## Data Storage - 143

1. What is the default location where the cassandra stores its data files?
2. `commitlog_directory`, `data_file_directories`. Explain why it is plural, `data_file_directories` (directories)?
3. What is the recommendation for production environment regarding the values of `commitlog_directory` and `data_file_directories`?
4. Explain `disk_failure_policy` and `commit_failure_policy`, what are they used for and what are possible values?

## Starup and JVM Settings

1. What is contained in `conf/cassandra.env.sh`?
2. What is `conf/logback.xml`?
