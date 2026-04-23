Implementation Evidence

S3 Bucket – Secure Vault Configuration









Private S3 bucket configured as the secure vault. Public access is fully blocked to enforce a zero-trust boundary and eliminate unintended exposure.



\--



S3 Permissions – Public Access Block





Account- and bucket-level public access settings are explicitly disabled, ensuring no objects can be accessed outside authenticated IAM policies.



\--





IAM User – Vault Guard Identity





Dedicated IAM identity created exclusively for programmatic access. Console login is disabled, reducing the attack surface and enforcing controlled access paths.



\--



IAM Policy – Least Privilege Enforcement





Custom policy granting only the minimum required permissions (ListBucket, PutObject, GetObject). Access is tightly scoped to a single S3 bucket and its objects using explicit ARNs.



\--



AWS CLI – Secure Local Configuration





Local environment configured using AWS CLI with access keys tied to the restricted IAM user. Region alignment ensures correct resource targeting.



\--



Access Control Validation (Failure Case)





Initial AccessDenied response confirms that permissions are not overly permissive. This validates enforcement of least privilege before policy refinement.



\--



Secure File Upload – Command Execution





Controlled upload operation executed via AWS CLI, demonstrating secure interaction between the local environment and the cloud vault.



\--



Upload Success – Verified Data Transfer





Successful object upload confirms that permissions are correctly scoped and functional without granting excessive access.



\-- 

&#x20;

S3 Object Verification – Cloud Confirmation





Final verification in the AWS Console showing the uploaded object present in the secure vault, completing the end-to-end workflow.



Security Insight



This implementation demonstrates that effective cloud security is not about blocking access entirely. It is about precisely controlling access paths, identities, and permissions.



Each component (S3, IAM, CLI) is intentionally constrained to enforce:



* Identity isolation
* Resource scoping
* Minimal privilege execution



This reflects a practical application of Zero Trust Architecture in AWS.

