# Emqx
![GitHub last commit](https://img.shields.io/github/last-commit/DanialNabiyan/Emqx-cluster)
[![GitHub license](https://img.shields.io/github/license/DanialNabiyan/Emqx-cluster)](https://github.com/DanialNabiyan/Emqx-cluster/blob/main/LICENSE)
![LinkedIn](https://shields.io/badge/style-DanialNabiyan-black?logo=linkedin&label=LinkedIn&link=https://www.linkedin.com/in/danial-nabiyan/)

The Most Scalable MQTT Broker for Iot , Industrial Iot and cloudnative application.
Connect any device, at any scale. Move and process your IoT data in real-time anywhere.

## Installation Ubuntu

```bash
curl -s https://assets.emqx.com/scripts/install-emqx-deb.sh | sudo bash
sudo apt-get install emqx
sudo systemctl start emqx
```
## Installation Redhat

```bash
curl -s https://assets.emqx.com/scripts/install-emqx-rpm.sh | sudo bash
sudo yum install emqx -y
sudo systemctl start emqx
```
# Create Cluster
with cluster you can High available your emqx and don't have any single point of failure 
and if one node or more fail your operation still working

- Node Name

  Emqx identified nodes with by names
  Node Name have two part that separated with @, like `emqx@172.198.11.5` or `emqx@myhost.broker.com`
  First part is name and second part is IP or domain name

- Node Discovery

  This step is one of most important step that we must do to emqx can discover other nodes
  By default emqx use manual strategy to discover other nodes.

  | Strategy |  Description  |
  |:-----|:--------:|
  | manual | **Create a cluster through manual command** |
  | static | **Create a cluster using a static node list** |
  | dns  | Create a cluster using DNS A and SRV records |
  | etcd | Create a cluster via etcd |
  | k8s | Create a cluster via Kubernetes service |

  At this time we want cluster with manual and static startegy 
  
- Config File
  You can modify your emqx config file in `/etc/emqx/emqx.conf`

- Check Cluster Status
  `emqx_ctl` command use for users to manage, configure and query EMQX Broker.
  If you want see your cluster status use `emqx_ctl cluster status`
  and if your cluster is ok you see this out put
  ```bash
  emqx_ctl cluster status
  Cluster status: [{running_nodes,['emqx@s1.emqx.io','emqx@s2.emqx.io']}]
  ```
  
## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Feedback

If you have any feedback, please reach out to us at danial.nabiyan1382@gmail.com
