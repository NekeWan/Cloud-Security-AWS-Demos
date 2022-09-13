# CREATING IAM USERS, ATTACH POLICIES AND ADD MFA

Identity and Access Management is a service that you use to grant permissions to users who are using different AWS Services.

Under IAM in AWS, you are also allowed to set up MFA for users.

The process of creating a user is as follows:

Under IAM, you click on User and it will require you to add a username and configure the AWS access type the user will be granted.

There are 2 access types: programmatic and AWS Management Console. 
For programmatic, the user will be able to access a terminal while for Management Console, whihch is common, enables access to the console.

You will also need to set up a custom console password which the user will continue to use at all times

The next step requires you to set permissions for the User 

Under set permissions, click on Attach existing policies directly, this gives a list of readily available list of policies that will give access to the user to a particular service.
This could be under roles such as administrative access, auditing and compliance, or services such as S3 or EC2

Once the user is created, there will be new user credentials provided. 

AWS provides the credentials and a login link that the user will have to use to be granted the access assigned to them, they cannot login or access the permissions without it.

Best Practices for this: 

When there are multiple users to be granted similar permissions, instead of assigning each user at a time, it is advised that a user group is created with the 
policy with similar permissions and add users into the group, they will inherit the permissions. It helps to manage users better.

Also, not anyone is to be added into the Admninistrator Access group only those who are authorised to. 

MFA (Multi Factor Authentication), it is an extra layer of security and prevents attackers from directly accessing an account. 

Setting MFA for users: You click on a user and then navigiate to security credentials, it will provide a list of MFA devices you would want to assign.
The most appropriate in this case is Virtual MFA device which will require the users to have an authenticator app in their mobiles or computers.

Once the authenticator app is installed, a QR code will be provided for scanning, it is important to have it stored as the user can lose their passwords,
it is important in retrieving the user's account. After scanning the QR code, the app authenticator generates passwords and you will be required to type in 2 consecutive 
MFA codes to assign MFA.
