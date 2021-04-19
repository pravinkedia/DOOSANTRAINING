# DOOSANTRAINING


## CP4D Environment

### Login to the Open Shift CP4D Cluster

https://c109-e.us-east.containers.cloud.ibm.com:31885/oauth/token/display

Your API token is
j8-go7QGFk-JxEhMr_FCFxHutFKpdSGtTLBi8LqXhAc

Log in with this token

oc login --token=j8-go7QGFk-JxEhMr_FCFxHutFKpdSGtTLBi8LqXhAc --server=https://c109-e.us-east.containers.cloud.ibm.com:30916

Use this token directly against the API

curl -H "Authorization: Bearer j8-go7QGFk-JxEhMr_FCFxHutFKpdSGtTLBi8LqXhAc" "https://c109-e.us-east.containers.cloud.ibm.com:30916/apis/user.openshift.io/v1/users/~"

C:\Users\PRAVINKEDIA\Downloads\OCP>oc version

    Client Version: 4.6.17
    
    Server Version: 4.5.35
    
    Kubernetes Version: v1.18.3+cdb0358

### Get Node Status

oc get nodes

oc get nodes -o wide

oc get node --show-labels

oc adm  top nodes

https://docs.openshift.com/container-platform/4.1/nodes/nodes/nodes-nodes-viewing.html

### Get Pods status

oc get pods -A

oc get pods -A -o wide

oc adm top pods

### Get Jobs

oc get jobs 

oc get jobs -A

### Get Storage Class

oc get sc -A

### Get PVC

oc get pvc -A

### Get Service Accounts

oc get sa

oc get sa -A

### Get Non Working Pods status 

oc get pods -A | grep -v Completed | grep 0/

### CP4D Monitoring status

oc -n openshift-monitoring get routes

https://alertmanager-main-openshift-monitoring.roks-cluster-wdc07-cp4d-317ec00f62194b593815c26a27e030dc-0000.us-east.containers.appdomain.cloud/#/alerts

## CP4D Services

oc get pods -A | grep dv

oc get pods -A | grep db2wh

oc get pods -A | grep db2oltp

oc get pods -A | grep dmc

oc get pods -A | grep wkc

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

### Download the DCW and the Lift tool based on your platform and version

https://www.lift-cli.cloud.ibm.com/

### IBM LIFT DEMO ONLINE

https://www.youtube.com/embed/9sA1xY3W_OU?rel=0

### DB2 Monitoring Table Functions

https://github.com/pravinkedia/DB2WHMONITORING/

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

### DB2 BIGSQL Connectivity

https://zen-cpd-zen.roks-cluster-wdc07-cp4d-317ec00f62194b593815c26a27e030dc-0000.us-east.containers.appdomain.cloud/dmc/console/#open/bigsql/bigsql-1614324740723680?serviceInstanceNamespace=zen&serviceInstanceDisplayName=Db2-Big-SQL-1

### DB2 BIGSQL S3 Integration

ROLE DASHDB_ENTERPRISE_USER to user "CP4D@DOOSAN.COM";

https://github.com/pravinkedia/CP4DBIGSQLS3

