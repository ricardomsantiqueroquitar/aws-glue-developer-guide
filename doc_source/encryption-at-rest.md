# Encryption at Rest<a name="encryption-at-rest"></a>

AWS Glue supports data encryption at rest for [Authoring Jobs in AWS Glue](author-job.md) and [Developing Scripts Using Development Endpoints](dev-endpoint.md)\. You can configure extract, transform, and load \(ETL\) jobs and development endpoints to use [AWS Key Management Service \(AWS KMS\)](https://aws.amazon.com/kms/) keys to write encrypted data at rest\. You can also encrypt the metadata stored in the [AWS Glue Data Catalog](components-overview.md#data-catalog-intro) using keys that you manage with AWS KMS\. Additionally, you can use AWS KMS keys to encrypt job bookmarks and the logs generated by [crawlers](https://docs.aws.amazon.com/glue/latest/dg/add-crawler.html) and ETL jobs\.

You can encrypt metadata objects in your AWS Glue Data Catalog in addition to the data written to Amazon Simple Storage Service \(Amazon S3\) and Amazon CloudWatch Logs by jobs, crawlers, and development endpoints\. When you create jobs, crawlers, and development endpoints in AWS Glue, you can provide encryption settings by attaching a security configuration\. Security configurations contain Amazon S3\-managed server\-side encryption keys \(SSE\-S3\) or customer master keys \(CMKs\) stored in AWS KMS \(SSE\-KMS\)\. You can create security configurations using the AWS Glue console\.

You can also enable encryption of the entire Data Catalog in your account\. You do so by specifying CMKs stored in AWS KMS\.

**Important**  
AWS Glue supports only symmetric CMKs\. For more information, see [Customer Master Keys \(CMKs\)](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#master_keys) in the *AWS Key Management Service Developer Guide*\.  


With encryption enabled, when you add Data Catalog objects, run crawlers, run jobs, or start development endpoints, SSE\-S3 or SSE\-KMS keys are used to write data at rest\. In addition, you can configure AWS Glue to only access Java Database Connectivity \(JDBC\) data stores through a trusted Secure Sockets Layer \(SSL\) protocol\. 

In AWS Glue, you control encryption settings in the following places:
+ The settings of your Data Catalog\.
+ The security configurations that you create\.
+ The server\-side encryption setting \(SSE\-S3 or SSE\-KMS\) that is passed as a parameter to your AWS Glue ETL \(extract, transform, and load\) job\.

For more information about how to set up encryption, see [Setting Up Encryption in AWS Glue](set-up-encryption.md)\. 

**Topics**
+ [Encrypting Your Data Catalog](encrypt-glue-data-catalog.md)
+ [Encrypting Connection Passwords](encrypt-connection-passwords.md)
+ [Encrypting Data Written by Crawlers, Jobs, and Development Endpoints](encryption-security-configuration.md)