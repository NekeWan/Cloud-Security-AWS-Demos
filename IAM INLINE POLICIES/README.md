# IAM INLINE POLICIES

Inline policies are of use when you want to maintain a strict one-on-one relationship between a policy and the identity 
to which it is applied. This is to ensure the policy applied to this particular identity cannot be accidentally assigned to a different identity.

When using an inline policy, the permissions in the policy cannot be accidentally attached to the wrong identity. Also IMPORTANT to note: when you 
delete the identity in the management console, the policy set in it is deleted as well.

It should be noted that not all IAM users are created to perform functions within the AWS cloud environment this is where inline policies are useful.

Others are created just for the purpose of viewing files for example, Cloud Auditors who do assessments

Auditors can be given an IAM user with read-only permissions in AWS. This means, they can only view and report on the files
but cannot make any changes to them. This permission is in line with what they have to do.

This is a best practice as no third-party or outsider in any organization should have write or change permissions granted to them
with regards to private organization files. 

The process for this:

Login to your AWS Console, search for IAM and click on users.

As a username you can assign Auditor, or whichever identity it is that wants to view files, in this case, I used Auditor for easy rememberance.

On granting access type, you can tick both programmatic and Management Console, there is no cause for alarm here as the functions assigned 
will be on read-only basis.

Under console password,click on custom and assign them a unique password.
Then, "require password reset" box which requires a new password each time a user signs in, uncheck it.

The next step is for adding tags and for easy reference, I added a name, which was Auditor.

I then created user and downloaded the user credentials by clicking : Download csv, it contains the link that the user will use to login to the AWS Console.

Permissions for Users:
Notably, upto now the user doesn't have a policy attached so you have to attach an inline policy directly to the user to say what they can do.
The inline policy is ONLY SPECIFIC to this user.

Now attaching the policy to the Auditor, one way can be attaching the policy through JSON Code:

This policy can be searched on the internet such as "policy that allows read-only access to the IAM console". A JSON code will be provided. When this code is attached it will allow read-only access to the AWS console which is fit for a third-party. Click on permissions for the user Auditor, then click on JSON

Copy and paste the code to attach to the user and click on review policy. I named the policy as AuditorReadOnly and then click on create policy.

Now, we have a user: "Auditor" and the permission attached "AuditorReadOnly" so when this user logs in they'll have read-only permissions.

Permissions for services:
You can also give permissions for services. For example, you want to give read-only permissions one service only, specifically S3

Go back to Users, click on Auditor then click on add permission, you choose "attach existing policies directly".

Search for S3 read only access and click on the specific policy ReadOnlyS3. Click on next review and then on add permissions and that will be assigned.

The Auditor will only be able to view the S3 service only, without being able to make any changes to it.
