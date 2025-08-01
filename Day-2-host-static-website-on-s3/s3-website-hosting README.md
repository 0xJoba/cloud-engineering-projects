<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Joba Amunigun  
**Email:** jobaamunigun@gmail.com

---

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

In this project i will be demonstrating how to use S3 to host a static website. I'm doing this project to learn about AWS and Cloud Services and how they can be used to store objects in the Cloud AND even host websites .

### Tools and concepts

Services I used were Amazon S3 . Key concepts I learnt includes bucket policies, uploading static website files, index.html, bucket endpoint URLs , ACLs and how they control access to our bucket's objects
 

### Project reflection

This project took me approximately 1hr+ including demo time,quiz time and secret mission time .The most challenging part was uploading the folders into the bucket correctly, It was most rewarding to see the website go live and public to the world

---

## How I Set Up an S3 Bucket

Creating an S3 bucket took me about 5 -10 minutes- I took how time to learn a few new concepts like enabling ACLs and Block Public Access. It should take about 2 minutes in the future

The Region I picked for my S3 bucket was Ohio
us-east-2 because it is the closest - it's best practice to pick the region close to you because it lowers the time to retrieve your things (aka latency) and costs(although this might not be important for this project - just best practice)

S3 bucket names are globally unique! This means that no other Amazon S3 buckets in the entire world can have the same bucket name (unless an existing bucket name is deleted). They have to be completely unique regardless of the region or Amazon Id

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### index.html and image assets

I uploaded two files to my S3 bucket - they were an index.html file ,this determines the structure (i.e what goes inside the website) and a folder of images and assets (i.e this will fill in the website with images and things to look at )







index.html



NextWork - Everyone...love_files.zip

Both files are necessary for this project as files needed as index for html determines the structure . However, the structure alone doesn't illustrate the content of the website (i.e if index.html says "insert image here",it might not have the actual image to display - i need to supply that image seperately that is why i have two image uploaded . The index.html file to direct what is inside the website page ,but also a bunch of assets like images that the website is trying to display)

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

Website hosting means putting websites files on a webserver which is a computer designed to turn the website into a website page that people can visit .Hence, making the website public on the internet.

To enable website hosting with my S3 bucket, I went into the properties tab of the bucked and enabled  
Static web hosting and also labeled "index.html" as the index document (i.e this is the document i am trying to host)



 

An ACL aka Access Control List is a way to configure permission settings inside a bucket .I enabled ACLs so that i can control access to my website files later. Although AWS recommends disabling ACLs . I will be enabling it to learn how ACLs work and compare it to bucket policies later 

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

Once static website is enabled, S3 produces a bucket endpoint URL which is a URL that takes anyone with the link to the website that i am hosting 

When I first visited the bucket endpoint URL, I saw an ERROR and that error is called a 403 Forbidden error. The reason for this error was that objects in the bucket are public by default - Even though i switched off the "Block all public access" .The website files themselves are still completely private inside . I need to manage their access settings privately - They need to be public files too for the public to see the contents of my website

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

To resolve this 403 Forbidden error, I updated the access  settings inside the bucket files .Using ACLs i made my bucket file public and when i checked my URL (Bucket end point) i could see a webpage all loaded up

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

An alternative to ACLs are bucket policies, which are rules that determines who is allowed or not allowed to do something. The benefit of using bucket policies is that you can have greater control of the ACTIONS that people are allowed or not allowed to do . while ACLs are useful for controlling public access to individual objects inside the bucket

My bucket policy denies everyone from deleting the "index.html " file. I tested this by trying to delete the uploaded "index.html" file and saw a permission denied ERROR message pop up - This suggests that the bucket policy added worked . It successfully stopped me from deleting the objects i wanted to protect

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-host-a-website-on-s3_sm2sm2sm)

---

---
