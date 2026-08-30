# Experiment 7 – Hadoop Single Node Cluster

## Title
Install Hadoop Single Node Cluster and Run Simple Applications like WordCount

## Aim
To find a procedure to set up a one-node Hadoop cluster.

---

## Requirements
| Item | Details |
|------|---------|
| OS | Ubuntu Linux (inside VirtualBox VM) |
| Java | OpenJDK 7 (java-7-openjdk) |
| Hadoop | 2.7.0 |
| SSH | openssh-server |
| Shell | Bash |

---

## Introduction to Hadoop

**Apache Hadoop** is an open-source framework for distributed storage and processing of large datasets using the MapReduce programming model. It is a core technology in Big Data and Cloud Computing.

### Hadoop Components:
| Component | Description |
|-----------|-------------|
| **Hadoop Common** | Shared utilities and libraries |
| **HDFS** | Hadoop Distributed File System – fault-tolerant storage |
| **YARN** | Yet Another Resource Negotiator – resource management |
| **MapReduce** | Distributed data processing framework |

---

## Procedure

### 1. Update System
```bash
sudo apt-get update
```

### 2. Install Java
```bash
sudo apt-get install openjdk-7-jdk
sudo apt-get install openjdk-7-jre
java -version
```

### 3. Install SSH Server
```bash
apt-get install openssh-server
ssh-keygen -t rsa -P "" -f ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
```

### 4. Create Hadoop User and Group
```bash
sudo addgroup hadoop
sudo adduser --ingroup hadoop hadoop
```

### 5. Download and Extract Hadoop 2.7.0
```bash
sudo tar -xzvf hadoop-2.7.0.tar.gz -C /usr/local/lib/
sudo chown -R hadoop:hadoop /usr/local/lib/hadoop-2.7.0
```

### 6. Create HDFS Directories
```bash
sudo mkdir -p /var/lib/hadoop/hdfs/namenode
sudo mkdir -p /var/lib/hadoop/hdfs/datanode
sudo chown -R hadoop /var/lib/hadoop
```

### 7. Configure Environment Variables (in `~/.bashrc`)
```bash
export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64
export HADOOP_INSTALL=/usr/local/lib/hadoop-2.7.0
export PATH=$PATH:$HADOOP_INSTALL/sbin:$HADOOP_INSTALL/bin
```

Then:
```bash
source ~/.bashrc
```

### 8. Configure Hadoop XML Files
Edit:
- `core-site.xml` – HDFS address
- `hdfs-site.xml` – Replication, NameNode/DataNode directories
- `mapred-site.xml` – MapReduce framework
- `yarn-site.xml` – YARN services

See `setup.txt` for full XML configurations.

### 9. Format NameNode and Start Hadoop
```bash
hdfs namenode -format
start-dfs.sh
start-yarn.sh
jps
```

---

## Files
| File | Description |
|------|-------------|
| `setup.txt` | Detailed installation and configuration steps |
| `output.txt` | Simulated terminal output |

---

## Optional Supporting Example

> **Note:** The manual documents the Hadoop single-node setup procedure. The WordCount application is the standard first MapReduce example. If required by the instructor, a `WordCount.java` can be compiled and submitted as a jar using:
> ```bash
> hadoop jar wordcount.jar WordCount /input /output
> hdfs dfs -cat /output/part-r-00000
> ```

---

## How to Execute
This is a configuration/installation experiment.
1. Follow the steps in `setup.txt` on an Ubuntu VM.
2. Verify Hadoop is running with `jps`.
3. Access the web UI at `http://localhost:50070/`.

---

## Expected Output
```
java version "1.7.0_79"
Hadoop 2.7.0
NameNode, DataNode, SecondaryNameNode, ResourceManager, NodeManager (via jps)
```

---

## Result
The procedure for setting up a one-node Hadoop cluster was completed successfully. Java, SSH, the Hadoop user, HDFS directories, and environment variables were all configured.
