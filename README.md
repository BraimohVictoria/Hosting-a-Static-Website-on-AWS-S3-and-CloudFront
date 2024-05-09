Hosting a Static Website on AWS S3 and Connecting to CloudFront:

Static websites typically contain HTML pages, images, CSS files, sometimes JavaScript, and all the neccessary files needed to host a website. They're static because they don't change. When you open the website, you see the same information every time in the same order and place unlike a dynamic website that changes.

In AWS, Static websites are stored in 'something' called an S3 bucket. The bucket can be likened to be the host or container that holds all the files relating to the website.

AWS CloudFront on the other hand is a content delivery network (CDN) service. Its primary function is to deliver content, such as web pages, videos, images, and other files to users with high performance, low latency, and high transfer speeds.

So, when you use S3 to host your static website and CloudFront as a CDN, you get a scalable, reliable, and high-performance solution for delivering your website's content to users worldwide. 

This Documentation is divided into four simple parts.

*Part One: Creating a Bucket in Amazon Simple Storage (S3)

*Part Two: Uploading the Website's Files to Your Bucket

*Part Three: Connecting to CloudFront

*Part Four: Deleting and Clearing up Your Resources


Let's get started!

Part One: Creating a Bucket in Amazon Simple Storage (S3)

Step 1: In your AWS management console, search for S3 and click 'Create bucket' Ensure you are using the us-east-1 or N. Virginia region. 

![](./Screenshots/Step%201.jpg)

Step 2: Pick a bucket name. Your bucket name should be globally unique. 

![](./Screenshots/Step%202.JPG)

Step 3: Disable Access Control Lists (ACLs). By default, buckets and objects in S3 are private, meaning that only the bucket owner has access to them. Disabling ACL here means that access to the bucket and its content will be specified using policies. 

![](./Screenshots/Step%203.JPG)

Step 4: Uncheck 'Block Public Access' and acknowledge. Without this feature disabled, you won't be able to attach your bucket policy.

![](./Screenshots/Step%204.jpg)

Step 5: Create your bucket. 

![](./Screenshots/Step%205.JPG)

Step 6: Your bucket has been created successfully. Click on your bucket name.

![](./Screenshots/Step%206.JPG)

Part Two: Uploading the Website's Files to Your Bucket 

Step 1: It's time to add your website's contents. These include your html files and images. Click on the 'Objects' tab and click upload. 

![](./Screenshots/Step%207.jpg)

Step 2: Add all the neccessary files for the website. Scroll down and upload. 

![](./Screenshots/Step%208.jpg)
 

Step 3: Go back to the bucket and click on properties.

![](./Screenshots/Step%209.JPG)

Step 4: Scroll down to Static website hosting and edit 

![](./Screenshots/Step%2010.jpg)

Step 5: Enable Static website hosting. In the index document, type index.html in the space provided and save changes. 

![](./Screenshots/Step%2011.JPG)

Step 6: Reload your page or go back to static website hosting to see your website url. Copy and open on a new tab in your browser. Don't close this tab. 

![](./Screenshots/Step%2012.JPG)

Step 7: Your static website is live and has been hosted but you can't see the content yet. This is because you need to grant public access using a bucket policy. You need to set the right permissions using this policy for the public to read the content of your website.

![](./Screenshots/Step%2013.JPG)

Step 8: Go back to the bucket and click on the permissions tab.

![](./Screenshots/Step%2014a.JPG)

Step 9: Scroll down to Bucket policy and click edit. 

![](./Screenshots/Step%2014.JPG)

Step 10: Write your policy in the space provided. In this policy, "Sid" represents the Statement ID. It is used to identify the statement within the policy.

"PublicReadGetObject" is the specific permission allowed by the policy. It indicates that the statement grants permission for anyone to GET the objects within the bucket, allowing public read access.

![](./Screenshots/Step%2015.JPG)

Step 11: Save changes.

![](./Screenshots/Step%2015b.jpg)

Step 12: Go back to your browser and reload. Your website is now live and publicly accessible. 

![](./Screenshots/Step%2016.jpg)

Part Three: Connecting to CloudFront

Step 1: In your AWS management console, search for CloudFront

![](./Screenshots/Step%2017.JPG)

Step 2: Click on Create CloudFront Distribution

![](./Screenshots/Step%2018.jpg)

Step 3: Click on origin domain and select your bucket name.  

![](./Screenshots/Step%2019.jpg)

Step 4: Enable firewall

![](./Screenshots/Step%2020.JPG)

Step 5: In the default root, type index.html and leave all other configuration. Create your distribution.

![](./Screenshots/Step%2021.jpg)

Step 6: Allow the distribution to complete the deployment stage. Reload your page and copy your distribution domain name. Paste in a new tab on your browser.

![](./Screenshots/Step%2022.jpg)

Step 7: Here you go! Your website now has the 'cloudfront.net' extension.

![](./Screenshots/Step%2023.jpg)

Part Four: Deleting and Clearing up Your Resources

It's always best practice to delete every resources you created in AWS in order not to incur charges or accrue bills which would be deducted from your bank account. These resources are only meant to be kept if it's for production purposes else, delete and terminate all.

Step 1: Starting with S3, Click the checkbox beside your bucket name and then click on delete (highlighted in red).

![](./Screenshots/Step%2024.jpg)

Step 2: You'll get a prompt to empty the content of your bucket first before deleting. 

![](./Screenshots/Step%2025.jpg)

Step 3: To confirm, type 'permanently delete' in the space provided and then empty.

![](./Screenshots/Step%2026.jpg)

Step 4: Go back to the bucket again. Click on the bucket and delete.

![](./Screenshots/Step%2027.JPG)

Step 5: Confirm your delete request by typing the name of your bucket and then delete. Congratulations!

![](./Screenshots/Step%2028.JPG)

Step 6: Go to the cloudfront distribution and click on the distribution you created. You must disable cloudfront first before you can delete. So, click on disable.

![](./Screenshots/Step%2029.jpg)

Step 7: When disabled, click on it again to delete.

![](./Screenshots/Step%2030.jpg)

Step 8: Congratulations!

![](./Screenshots/Step%2031.JPG)

This documentation has walked you through the process of hosting a static website on AWS S3 and connecting to CloudFront. It's a seamless process and don't forget to terminate your resources when done!

'I'll see you in the clouds!'