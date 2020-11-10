Object storage
==============

1.Lustre

- Intel (since 2012)
- very big clusters (supercomputers)
- metadata server 
- InfiniBand RDMA, tcp\ip
- kernel FS module, FUSE

2.GlusterFS

- Red Hat since 2011
- FUSE
- works over ext3\4, xfs, ...
- InfiniBand RDMA, tcp\ip 
- not required standalone metadata server

3.Ceph

- Red Hat since 2014
- block and file storage
- builtin replication
- separate processing data and metadata

4.GFS, GFS2

- Red Hat
- journaled file systems
- all nodes - peers
- block device 
- targets SAN-like environments

5.OCFS2

- Oracle Cluster File System 

6.GPFS

- General Parallel File System
- IBM proprietary

7. Swift

- OpenStack Object Storage ("Swift")
- https://docs.openstack.org/swift/latest/overview_architecture.html#
- NVIDIA https://www.swiftstack.com/docs/introduction/openstack_swift.html
- SwiftStack is the lead upstream contributor to the OpenStack Swift project with around 20% of community activity in 2015.
