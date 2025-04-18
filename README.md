# AWS Storage Services Assignment

**1. Create an S3 bucket and upload, retrieve, and delete objects using the Management Console.**


**1. Create an S3 Bucket**


ii. Sign in to your AWS Management Console.

iii. Search for and open S3.

iv. Click "Create bucket".

v. Bucket Name: Enter a unique name (example: my-first-s3-bucket-oluwa).

vi. Region: Choose your region (example: US East (N. Virginia) or closest to you).

vii. Leave other settings default for now (you can uncheck "Block all public access" if you need public access later).

viii. Scroll down and click "Create bucket"


![Task](photos/tasks1_1.JPG)


**2. Upload an Object (like a file)**


i. Open your bucket by clicking on its name.

ii. Click "Upload" → "Add files".

iii. Select a file from your computer (e.g., photo.jpg or document.txt).

iv. Click "Upload" at the bottom.

Your file is now inside your bucket



![Task](photos/tasks2_1.JPG)


**3. Retrieve (Download) an Object**


i. Go inside the bucket and click on the object (file) name.

ii. Click "Download" to save it back to your computer.



![Task](photos/tasks3_1.JPG)


**4. Delete an Object**


i. Inside the bucket, select the checkbox next to the object.

ii. Click "Actions" → "Delete".

iii. Confirm the deletion.



![Task](photos/tasks4_1.JPG)


**2. Configure S3 bucket permissions to make objects public.**


To grant bucket permissions to make obects public.

i. Go to the AWS S3 Console.

ii. Click the bucket name you want to make objects public in.


**Disable "Block All Public Access"**

By default, AWS blocks public access (for security reasons), so you have to turn it off.

iii. Inside your bucket, click on the Permissions tab.

iv. Find "Block public access (bucket settings)".

v. Click Edit.

vi. Uncheck:

"Block all public access"

(You might also uncheck the 3 sub-options under it)

Acknowledge the warning by checking the box.

vii. Click Save changes.



![Task](photos/tasks1_2.JPG)


 **Add a Bucket Policy (to make objects public)**
 

vii. Still under the Permissions tab, scroll to Bucket Policy.

ix. Click Edit or Add Policy.

x. Paste this policy into the editor (replace your-bucket-name with your s3 bucket name) using this code:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

This policy allows anyone on the internet to view (read) your files.

xi. Click Save changes.



![Task](photos/tasks2_2.JPG)


**3. Collect HTML files from the frontend mentees and host them as a website on the S3 bucket.**

I got my HTML files to host on the website on the S3 bucket from Chidimma, A collegue from Frontend mentee.


**To Configure Bucket for Static Website Hosting.**


i. Inside the bucket, click Properties tab.

ii. Scroll down to Static website hosting.

iii. Click Edit.

iv. Select Enable.

vi. Index Document: Enter index.html.

(Optional) Error Document: Enter error.html if you have a custom error page.

v. Click Save changes.

vi. Go back to Properties → Static Website Hosting.

vii. You’ll see a Website endpoint URL (something like http://your-bucket-name.s3-website-us-east-1.amazonaws.com).

Boom! website is live.



![Task](photos/tasks1_static_1.JPG)



![Task](photos/task1_static_2.JPG)



**4. Use AWS CLI to manage S3 buckets and objects.**


**Set Up AWS CLI First**

Before anything, make sure AWS CLI is installed:

i. Install AWS CLI:

Windows: Download installer from AWS CLI Download

Mac/Linux: Use brew install awscli or sudo apt install awscli

ii. Configure AWS CLI using this commmand;

aws configure

You'll be asked to enter:

iii. AWS Access Key ID

iv. AWS Secret Access Key

v. Region (e.g., us-east-1)

vi. Output format (e.g., json or text)

After all done, your computer can talk to AWS.



![Task](photos/tasks1_3.JPG)

**NOTE: DON'T EVER DISPLAY YOUR AWS SECRET ACCESS KEY ON A PUPLIC DOMAIN e.g GITHUB. THIS IS JUST FOR A DEMO.**

**Managing S3 Buckets and Objects via CLI**


**i. Create a New S3 Bucket using the command;**

aws s3 mb s3://your-bucket-name

'mb' = make bucket

Example;

aws s3 mb s3://mym4ace-bucket002



![Task](photos/tasks1_1.JPG)


**II. List All Buckets using the command**

aws s3 ls



![Task](photos/task1_upload_33.JPG)

This shows all the buckets you have.



**iii. Upload a File to S3 using the command**

aws s3 cp your-file.html s3://your-bucket-name/

Example;

aws s3 cp index.html s3://mym4ace-bucket002/



![Task](photos/task1_upload_3.JPG)

Files is uploaded.


**iv.Download (Retrieve) a File from S3 using the command;**

aws s3 cp s3://your-bucket-name/your-file.html your-local-folder/

Example;

aws s3 cp s3://mym4ace-bucket002/index.html Downloads/



![Task](photos/task1_upload_31.JPG)



**v. Delete an Object (File) using the command;**

aws s3 rm s3://your-bucket-name/your-file.html

rm = remove

Examples;

aws s3 rm s3://mym4ace-bucket002/your-file.html



![Task](photos/task1_upload_35.JPG)


The file is deleted.


**v. Delete a Bucket (only if it's empty) using the command;**

aws s3 rb s3://your-bucket-name

rb = remove bucket

Example;

aws s3 rb s3://mym4ace-bucket002



![Task](photos/task1_upolad_1.JPG)



![Task](photos/task1_upload_36.JPG)


###### where are you













