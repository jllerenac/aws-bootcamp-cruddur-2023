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

To install in gitpod. I updated gitpod.yml with an automated script 
![image](https://user-images.githubusercontent.com/46797181/221371091-622b739f-4db2-4b52-895c-d099bd149b8d.png)


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

 ### Generate credentials for created user 
 1. Go to IAM, click user and select the created account.
 2. Click on `security credentials` tab and then `enable console access`
 ![image](https://user-images.githubusercontent.com/46797181/220822624-6e8c8be1-91f5-4cb3-96e5-715f157ea6e2.png)
 3. Once in console access set up a password.

![image](https://user-images.githubusercontent.com/46797181/220822771-cb8befa8-7eed-491d-a715-65bcec36b8a4.png)

4. Log in with the account to verify access 
![image](https://user-images.githubusercontent.com/46797181/220823245-0bcbf320-d2e8-4ee7-8495-7a3352bc6668.png)

### USE CLOUD SHELL
1. Log in the console and click on the `CLI` icon on the upper right part of the window
![image](https://user-images.githubusercontent.com/46797181/220826113-83cbdb47-aef1-453d-8727-2c52a46ce9e9.png)
2. Once in the console enter `aws sts get-caller-identity` to see what user we are.
![image](https://user-images.githubusercontent.com/46797181/220826438-b88baee1-0703-47bc-91ba-bf65648184f7.png)

### Create a billing alarm

This is going to be done on command line via git pod. First make sure we have admin credentials set up in git pod
![image](https://user-images.githubusercontent.com/46797181/221371931-3dc458e8-f20d-4c7e-87ae-040d4886f71f.png)

We can verify in git pod settings
![image](https://user-images.githubusercontent.com/46797181/221372046-5ce37b03-3616-4db9-8412-0f49d0a3f22a.png)

We need to create a SNS topic, for this in the console we search for SNS and once selected there is an input field to create a topic
![image](https://user-images.githubusercontent.com/46797181/221372327-9920d55c-2fa3-4948-af0b-73fecca4075f.png)

We'll leave it as default and create the topic
![image](https://user-images.githubusercontent.com/46797181/221372429-cda9cc99-41fb-4841-a0c0-07b747a50ef4.png)

We can also create with AWS CLI by executing `aws sns create-topic --name AWSCloudBootcamp`
![image](https://user-images.githubusercontent.com/46797181/221372800-55da322b-d0f2-4b12-8f79-9ed297303687.png)

We subscribe by executing the command `aws sns subscribe --topic-arn arn:aws:sns:us-east-1:{accountID}:AWSCloudBootcamp --protocol email --notification-endpoint josellerenacarpio@gmail.com`
![image](https://user-images.githubusercontent.com/46797181/221373076-23f89501-ff0e-44a0-99e6-8e79f011a023.png)

We'll receive an email and click on the link to activate
![image](https://user-images.githubusercontent.com/46797181/221373154-22790584-0fcf-46c6-995f-5be3c7d0acb2.png)

We can see in the console as well
![image](https://user-images.githubusercontent.com/46797181/221373213-c4b9092a-7c98-4452-8e22-430732c19b5b.png)
