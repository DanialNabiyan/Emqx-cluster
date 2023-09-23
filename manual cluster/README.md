# Manual Cluster

For manual clustring you should use this document

In this example im cluster my emqx in two node but best practice is **three** node for cluster 

You can see configs in `emqx-server1.conf` and `emqx-server2.conf` , each config used in one server

**Note: You should change node name and cluster name to your custome values and cluster name must be same in all cluster nodes**

After you set your custome config you must restart your emqx service
```bash
systemctl restart emqx.service
```
# Join nodes to cluster

Go to the server2 that you want to join to server1 , run this command

```bash
emqx_ctl cluster join emqx2@192.167.125.5
```

At this example im join `emqx2@192.167.125.5` to `emqx@192.167.125.2`

After that run this command to see cluster status

```bash
emqx_ctl cluster status
```
