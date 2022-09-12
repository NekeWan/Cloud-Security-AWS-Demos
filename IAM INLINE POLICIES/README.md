# IAM INLINE POLICIES

It should be noted that not all IAM users are created to perform functions within the AWS cloud environment.

Others are created just for the purpose of viewing files for example, Cloud Auditors who do assessments

Auditors can be given an IAM user with read-only permissions in AWS. This means, they can only view and report on the files
but cannot make any changes to them. 

This is a best practice as no third-party or outsider in any organization should have write or change permissions granted to them
with regards to private organization files. 
