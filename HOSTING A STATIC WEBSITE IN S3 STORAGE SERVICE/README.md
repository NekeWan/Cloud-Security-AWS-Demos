# HOSTING A STATIC WEBSITE IN AMAZON S3 STORAGE SERVICE

Hosting a static website in Amazon S3 for companies has become a viable, cost-effective alternative, it eases the burden on the company to house
servers and on premises infrastructure and not to mention, the extra cost of enforcing physical security for the premises.

S3 is an Amazon service shortened from Simple Storage Service. It is used in storing unlimited amounts of data.

AWS has regions placed around the world, region- is a seperate geographic area such as N. America, South Africa, Middle East, Asia Pacific to state a few. 
Regions can be in a country or across countries, for an example I'll use N.Virginia found in N.America.

When creating a storage service you have to specify a region that is, if your company is in N.Virginia, you choose N.Virginia and create a bucket.

A Bucket is like a major folder holding subfolders and files within it. 

Besides storage, S3 can also be used to host your static website. A static website contains stable content, users see the exact same thing on each page,
you don't need to login to access the information. The opposite is a dynamic website where each user can access different content on request, they can login
and access their own content.

Creating an S3 Bucket & Hosting a static website process:

You will need a source code and these can be easily accessed on websites in the internet where developers store codes for static and dynmaic websites.
Download a code from the website, and extract the code in your desktop.

Go back to AWS Console and search for S3, once it loads, click on Buckets and then, create Bucket

Bucket names MUST be unique to all users, in my case, I named it nekestaticwebsite. Remember to specify the region while creating the S3 bucket.

In this case, the website will be publicly accessible however, this is not recommended in real life scenarios. So, uncheck the "Block all public access"
Amazon will ask if you acknowledge you are allowing public access to your bucket, check the acknowledge box.

As best practice, under encryption that follows right after, choose enable and use AWS Keys. Then create Bucket.

This has now created nekestaticwebsite Bucket, the next step is adding the source code you downloaded and extracted in your desktop.

Click on the new bucket and open it, choose upload, this will lead to ask you either add files or folders, I put the extracted code in a folder
and so I chose add folder and dragged the folder into the specific bucket.

Then, expand Destination and enable bucket versioning. Click on upload to upload the folder and exit.

Click on properties and look for static website hosting, click on edit and enable.

Hosting type remains as "host a static website".Scroll down to static website hosting and click to load the website!

403 Forbidden Error?! That's the best part, encountering a problem and finding a way to troubleshoot it!

Your website will most likely get a 403 error but it's Amazon's doing, because of it's security measures, you allowed public access to your bucket
Amazon did not receive a permission to do so. 

Go back to Bucket, then permissions. Click on Access Control List (ACL) and edit. Search for an S3 read-only policy, this is because, users of the static website 
can only view content, no other actions are required. You can browse the internet for let's say..."Granting read-only permission to an anonymous user"
a JSON code will be provided for this. 

You;'re required to add a bucket policy so that your website can be seen by users. Copy the JSON cide given by AWS and within the code, there's
a line where you have to copy the name of your website and save!

When you reload, your static website will be visible! Now you can pat yourself on the back. You did it!

