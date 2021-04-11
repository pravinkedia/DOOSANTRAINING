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

### Get Pods status

### Get Storage Class

### Get PVC

### Get Service Accounts

### Get Non Working Pods status 


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

