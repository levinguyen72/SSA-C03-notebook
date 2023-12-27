# Key terms 1
- Direct (local) attached storage: directly store on EC2 instance host
- Network - attached storage: volume delivered over the network EBS - Elastic Block Store
- Ephameral - storage: temporary storage
- Persistent - storage: permanent storage, live on past the life time of instance
# Key terms 2
- Block storage - storage: volume present to the OS as collection of blocks, no structure provide. Mountable, Bootable.
- File storage - storage: present fileshare. Mountable, unbootable
- Object storage: collection of object, flat. Mountable, unbootable 

# Storage performance
IO x IOPS = throughput 

# EBS - Elastic Block Store
- Definition
![](../assets/Screenshot%202023-12-26%20at%2017.04.03.png)
- Visibility
![](../assets/Screenshot%202023-12-26%20at%2017.12.23.png)
- **Volume type** 
- *SSD base*
  - gp3: 3000 IOPS & 125MiB/s standard volume size, ~ 20% cheaper than gp2
  - gp2: 1GB to 16TB volume, 16000 IOPS and 1000MiB/s
  - io1: 260000 IOPS, 7500 MB/s
  - io2: 160000 IOPS, 4750MB/s
- *HHD base*
  - st1: (data warehouse, big data, log processing) max 500 IOPS
  - sc1: max 250 IOPS, 250 MB/s

# Instance Store Volume
- Pros:
  - Much more IOPS and throughput vs EBS with the equivalent machine power
  - D3 4.6 GB/s throughput
  - I3 16GB/s throughput
  - Pay for it anyway - include instance price
- Cons: 
  - Local on EC2 host
  - Add at launch only
  - Lost on instance move, resize or failure
  - Temporary
# Instance store volume vs EBS
- Persistence -> EBS
- Resilience -> EBS
- Storage isolated from *instance lifecycle* -> EBS
- Super high performance need - Instance store
- Cost - Instance store
![](../assets/Screenshot%202023-12-27%20at%2011.29.11.png)

# EBS snapshots 
- Definition
  - Snapshots are incremetal volume copy to S3
  - First is full copy of the data on the volume
  - Future snaps are incremental
  - Volume can be created/restored from snapshots
  - Snapshot can be copied from another region
- EBS snapshots & volume performance
  - New EBS volumn, full performance immediately
  - Snaps restrore lazily - fetch gradually
  - Requested block are fetch immediately
- Snapshot consumption and billing
  - Gigabybe month
  - Use not allocated data