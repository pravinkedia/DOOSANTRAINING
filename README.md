# DOOSANTRAINING


## CP4D Environment

### Login to the Cluster

https://c109-e.us-east.containers.cloud.ibm.com:31885/oauth/token/display

Your API token is

9l90pv1kib-MV3ZZXi8NXUOqxYxJReyD0YHL0zKl0Nw

Log in with this token

oc login --token=9l90pv1kib-MV3ZZXi8NXUOqxYxJReyD0YHL0zKl0Nw --server=https://c109-e.us-east.containers.cloud.ibm.com:30916

Use this token directly against the API

curl -H "Authorization: Bearer 9l90pv1kib-MV3ZZXi8NXUOqxYxJReyD0YHL0zKl0Nw" "https://c109-e.us-east.containers.cloud.ibm.com:30916/apis/user.openshift.io/v1/users/~"

C:\Users\PRAVINKEDIA\Downloads\OCP>oc version
    Client Version: 4.6.17
    Server Version: 4.5.35
    Kubernetes Version: v1.18.3+cdb0358

### Get Node Status

oc get nodes

oc get nodes -o wide

oc get nodes show-labels

oc adm  top nodes

https://docs.openshift.com/container-platform/4.1/nodes/nodes/nodes-nodes-viewing.html

### Get Pods status

### Get Storage Class

### Get PVC

### Get Service Accounts

### Get Non Working Pods status 

### CP4D Monitoring status

oc -n openshift-monitoring get routes

https://alertmanager-main-openshift-monitoring.roks-cluster-wdc07-cp4d-317ec00f62194b593815c26a27e030dc-0000.us-east.containers.appdomain.cloud/#/alerts

## CP4D Services



## DB2 WAREHOUSE EXERCISE

### DB2 Connections

#### DB2 warehouse connection
jdbc:db2://10.191.195.39:32732/BLUDB:user=dev3;password=ibmindia@trainer;securityMechanism=9;encryptionAlgorithm=2

#### DB2 Bigsql connection
jdbc:db2://10.191.195.39:31737/bigsql:user=dev3;password=ibmindia@trainer;

#### DB2oltp connection
jdbc:db2://10.191.195.39:31395/BLUDB:user=cp4d@doosan.com;password=123qwer@;securityMechanism=9;encryptionAlgorithm=2

### DB2 Exercise using tables in DEV3 schema in DB2 Warehouse

#### DB2 Date Time functions	
https://developer.ibm.com/technologies/data-management/articles/fun-with-dates-and-times/

#### DB2 OLAP and Analytics functions	
https://www.ibm.com/support/knowledgecenter/sr/SSEPGG_11.5.0/com.ibm.db2.luw.sql.ref.doc/doc/r0061949.html

https://www.ibm.com/support/knowledgecenter/sr/SSEPGG_11.5.0/com.ibm.db2.luw.sql.ref.doc/doc/r0011043.html

https://www.ibm.com/support/knowledgecenter/sr/SSEPGG_11.5.0/com.ibm.db2.luw.sql.ref.doc/doc/r0061840.html

https://www.ibm.com/support/knowledgecenter/SSFMBX/com.ibm.swg.im.dashdb.sql.ref.doc/doc/r0023461.html

#### DB2 OLAP Functions	
https://www.wisdomjobs.com/e-university/db2-using-sql-tutorial-283/olap-functions-definitions-1690.html

https://www.idug.org/browse/blogs/blogviewer?blogkey=de6955ad-e3cf-48f6-84b5-619afcf83c28

#### DB2 Aggregate Functions	
https://www.db2tutorial.com/db2-aggregate-functions/
https://www.db2tutorial.com/db2-window-functions/db2-rank/

#### DB2 ROW Number functions	
https://www.daharveyjr.com/numbering-rows-in-db2-with-row_number-and-partition-by/

#### DB2 Intersect, except functions	
https://www.datavail.com/blog/using-intersect-and-except-in-db2/

https://www.db2tutorial.com/db2-basics/db2-intersect/

#### DB2 Create External Table on S3
create external table et_bank_customers SAMEAS bank_customers using  
(
dataobject 'bank_customers.csv'
delimite ','
nullvalue ''

s3('s3-api.us-geo.objectstorage.softlayer.net',
    'api key',
    'api secret',
    'bucketname'
)

);

insert into bank_customers select * from et_bank_customers;

