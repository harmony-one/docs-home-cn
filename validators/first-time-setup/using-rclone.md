# Syncing with Rclone使用Rclone进行同步

{% hint style="warning" %}
This document introduces another centralized fast state syncing method using rclone. Please use it with caution. This guide is mainly used for a newly started node to catch up with the blockchain faster. Otherwise, the blockchain syncing may take weeks.‌

本文档介绍了另一种使用rclone的集中式快速状态同步方法。请谨慎使用。本指南主要用于新启动的节点，以更快地赶上区块链。否则，区块链同步可能需要数周时间。
{% endhint %}

Rclone db snapshot is sync'ed with blockchain frequently. However, there maybe a potential race condition when the rclone may fail due to our nodes were updating the db files at the same time. In this case, just re-run the rclone command to re-sync again.‌

Rclone数据库快照经常用于与区块链同步。但是，如果我们的节点在同时更新db文件则会导致rclone失败时。在这种情况下，只需重新运行rclone命令以再次重新同步。

## 1. Installing Rclone安装Rclone <a id="1-installing-rclone"></a>

‌

For installing Rclone, please follow the instructions at [https://rclone.org](https://rclone.org/).‌

要安装Rclone，请按照[https://rclone.org上的说明进行操作。](https://rclone.org上的说明进行操作。)

## 2. Configuring Rclone 配置Rclone <a id="2-configuring-rclone"></a>

To check the location of the `rclone.conf`file run: 要检查rclone.conf文件的位置，请运行：

```text
rclone config file
```

The `rclone.conf` file is usually located at `~/.config/rclone/rclone.conf` . Now edit the file and add the information below: rclone.conf文件通常位于〜/ .config / rclone / rclone.conf中。现在编辑文件并添加以下信息：

```text
[mainnet]type = s3provider = AWSenv_auth = falseregion = us-west-1acl = public-readserver_side_encryption = AES256storage_class = REDUCED_REDUNDANCY
```

## 3. Running Rclone 运行Rclone <a id="3-running-rclone"></a>

Below is the command to sync the shard you want. Replace `<ShardID>`with the shard number you want to sync. 以下是同步所需分片的命令。将替换为要同步的分片号。

```text
rclone sync mainnet:pub.harmony.one/mainnet.min/harmony_db_<ShardID> harmony_db_<ShardID>
```

Nodes in shard 0 just need to sync `harmony_db_0`

Nodes in shard 1, 2, 3 need to sync both `harmony_db_0`, and `harmony_db_<ShardID>`

分片0中的节点仅需要同步harmony\_db\_0

分片1、2、3中的节点需要同步`harmony_db_0`和`armony_db_<ShardID>`

