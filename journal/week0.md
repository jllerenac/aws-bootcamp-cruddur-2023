# Week 0 — Billing and Architecture

## Required homework

Attended the live streaming. In the live session followed the steps to creat the architecture diagram

Watched Chirag's spending consideration 20 minute video

Answered the security quiz questions. I did research for some questions that I was not sure. 

### Watched and follow Chirag's video for security considerations.

Set up MFA for account
![image](https://user-images.githubusercontent.com/46797181/220008680-00fa978c-8611-49c3-941d-a1734469e0a4.png)

Checked for to create organizations and enable cloudtrail

### LUCID DIAGRAM

Below the links for the diagram created with AWS icons and added security feature
https://lucid.app/documents/view/10cdb4b7-335d-4e05-935f-3769a3be26be

Below the link for the simple diagram followed in the live stream
https://lucid.app/lucidchart/invitations/accept/inv_1fa98927-ee9c-4156-a297-75e7d0ed60ef


### Install AWS CLI
As I have practiced with AWS before. I already have **aws** installed in my local machine.

I use Ubuntu, so simply with **sudo apt install awscli** is good enough 

Below a PoC image.

![awscli](https://user-images.githubusercontent.com/46797181/219274204-c7ffbc00-e046-4395-9dea-b23023c85862.png)

### CREATE AWS BUDGET
1. Log in the console and search for `AWS Budget` in home dashboard, then click on it
![image](https://user-images.githubusercontent.com/46797181/220817067-61606e1b-c532-42ef-ae38-6938a64261e5.png)

2.Click on `Create budget` and select the desired templates and specified the name and budget amount if is the case, then click on `Create budget`

![image](https://user-images.githubusercontent.com/46797181/220816886-bd459a29-dfa6-4185-bcb4-2bfebca16019.png)
![image](https://user-images.githubusercontent.com/46797181/220816956-9e53bc7d-982e-4fe8-8572-a9fc63b779e6.png)

### CREATE AN ADMIN USER
1. Go to IAM, click on `users` then `add users`
![image](https://user-images.githubusercontent.com/46797181/220819904-f3f5802d-8929-4f29-8607-b10bacec1ed5.png)


2. Give the user a name and either create a new group or include it in an existing one. In this case an admin group already exists
![image](https://user-images.githubusercontent.com/46797181/220820080-29bdf5b9-5663-4f48-98af-d4919e0a3973.png)

3. Create the user and we can verify that user is created and is part of the administrator group.
![image](https://user-images.githubusercontent.com/46797181/220820321-4f5e5de9-db03-4923-8e0d-45e9441da9d3.png)
 
 
 ### Create an account alias.
 In IAM dashboard click on `create` or `edit` to set up an account alias
 ![image](https://user-images.githubusercontent.com/46797181/220821317-c5da7c8e-8143-4c51-9ade-507857f588b0.png)

 
