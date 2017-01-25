# Elasticsearch-with-Kafka
Deployment step by step for ElkStack with Kafka

Elasticsearch (2.4.1) cluster on top of OpenStack Kilo.

Elasticsearch best-practices recommend to separate nodes in three roles:

    Master nodes - intended for clustering management only, no data, no HTTP API
    Client nodes - intended for client usage, no data, with HTTP API
    Data nodes - intended for storing and indexing your data, no HTTP API

Given this, I'm going to demonstrate how to provision a (near, as storage is still an issue) production grade scenario consisting of 3 master (Recommanded), 2 client and x data nodes (Depend on data).

(Important notes)

Please keep in mind JAVA_OPTS has defined by default in elasticsearch like below.


    By default, ES_JAVA_OPTS is set to -Xms256m -Xmx256m. This is a very low value but many users, i.e. Myself, were having issues with pods getting killed because hosts were out of memory. You can change this yourself in the deployment descriptors available in this repository.
    
    Pre-requisites.
    
   1:- Need to intsall Latest OpenJDK
   2:- Need to deploy all nodes in one subnet
 


