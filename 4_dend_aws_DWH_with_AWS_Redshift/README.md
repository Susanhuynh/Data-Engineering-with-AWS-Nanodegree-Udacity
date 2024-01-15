**1. Create IAM Role**
All AWS services require identity and Access Management (IAM) policies, roles and their associcated permissions. Creating IAM user role to have permission to use the Redshift service on AWS.

**2. Create Security Group**
A security group will act as firewall rules for your Redshift cluster to control inbound and outbound traffic

**3. Create an IAM User**

**4. Launch A Redshift Cluster**

**5. Create Existing Bucket**
Details of an Existing Bucket

a. Properties
There are several properties that you can set for S3 buckets, such as:

Bucket Versioning - Allows you to keep multiple versions of an object in the same bucket.
Static website hosting - Mark if the bucket is used to host a website. S3 is a very cost-effective and cheap solution for serving up static web content.
Requester pays - Make the requester pays for requests and data transfer costs.
Server access logging - Log requests for access to your bucket.

b. Permissions
It shows who has access to the S3 bucket, and who has access to the data within the bucket. In the example snapshots above, the bucket is public, meaning anyone can access it. Here, we can write an access policy (in JSON format) to provides access to the objects stored in the bucket.

c. Metrics
View the metrics for usage, request, and data transfer activity within your bucket, such as, total bucket size, total number of objects, and storage class analysis.

d. Management
It allows you to create life cycle rules to help manage your objects. It includes rules such as transitioning objects to another storage class, archiving them, or deleting them after a specified period of time.

e. Access points
Here, you can create access endpoints for sharing the bucket at scale. Using an endpoint, you can perform all regular operations on the bucket.

**6. Creating AWS Relational Database Service (RDS)**
AWS RDS is a managed PostgresSQL service. Amazon RDS is a relational database service that manages common database administration tasks, resize automatically and is cost-friendly.

There are two methods to create a database that AWS provides two options to choose from:
- Standard create - You have set all of the configuration options, including ones for availability, security, backups, and maintenance.
- Easy create - You use the industry best-practice configurations. All configuration options, except the Encryption and VPC details, can be changed after the database is created.

**7. Infrustructure as Code**
The advantages of Infrastructure as Code over creating Infrastructure by clicking around:
- Sharing: One can share all the steps with others easily
- Reproducibility: One can be sure that no steps are forgotten
- Multiple deployments: One can create a test environment identical to the production environment
- Maintainability: If a change is needed, one can keep track of the changes by comparing the code.

