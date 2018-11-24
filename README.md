Regular Issue:
    Apache Hadoop
    CDH : Cloudera Distributed Hadoop 
    HDP : Hortonworks Data Platform
  
    CDH 70~80% Percetage Domestic
    HDP 10~20% Percetage Domestic

    CDH cooperate with spark closely.

    Support CentOS and Ubuntu

Operation Step:
    1. disable firewall
    2. hdfs namenode -format
    3. start-dfs.sh 
    

Legacy Issue:
    1. Distributed Hadoop Support.
    2. Comprihension Further on Hadoop Basis.
    

Reference:
    https://github.com/andrewrothstein/ansible-hadoop.git
    https://github.com/grycap/ansible-role-hadoop.git


[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-hadoop.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-hadoop)

Hadoop Cluster Role 
===================

Installs and configure Hadoop system (version 2.X) in a cluster of nodes.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

	# The type of the node: slave or master or resourcemanager or nodemanager or datanode or namenode 
	hadoop_type_of_node: slave
	# Hadoop base directory to install the software
	hadoop_home: /opt/hadoop-2.X
	# List of servers to download the hadoop code
	hadoop_mirrors: [ "http://mirror.cc.columbia.edu/pub/software/apache/hadoop/core/stable2/",
			"http://ftp.osuosl.org/pub/apache/hadoop/core/stable2/",
			"http://apache.rediris.es/hadoop/core/stable2/",
			"http://www-eu.apache.org/dist/hadoop/common/stable2/" ]
	# Hadoop version to install
	hadoop_version: 2.7.3
	# A dictionary with a set of properties to set in the core-site.xml
	hdfs_props: {}
	# A dictionary with a set of properties to set in the yarn-site.xml
	yarn_props: {}

Example Playbook
----------------

This an example of how to install the Cluster:

In the "Worker Nodes"
```yml
  roles:
    - { role: 'grycap.hadoop', hadoop_master: 'MASTER_NODE_NAME_OR_IP' }
```

In the "Manager Node"
```yml
  roles:
    - { role: 'grycap.hadoop', hadoop_master: 'MASTER_NODE_NAME_OR_IP', hadoop_type_of_node: 'master'}
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks



