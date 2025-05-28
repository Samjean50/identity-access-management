# Mini Project - AWS Identity and Access Management

## Table of Contents

1. Project Overview  
   - 1.1 [Project Goals and Requirements](#11-project-goals-and-requirements)  
   - 1.2 [Use Case](#12-use-case)

2. Project Tasks  
   - 2.1 [Part 1 - Policy and User Setup](#21-part-1---policy-and-user-setup)  
   - 2.2 [Part 2 - Group and Role-Based Access](#22-part-2---group-and-role-based-access)

3. Troubleshooting  
4. Conclusion  


### 1. Project Overview

This mini project focuses on using AWS Identity and Access Management (IAM) to create and manage users, groups, roles, and policies. The goal is to implement secure access control for AWS resources, demonstrating a practical understanding of IAM best practices and configurations.

#### 1.1 Project Goals and Requirements

* Understand AWS IAM principles and components.
* Learn to create and manage IAM policies.
* Apply IAM concepts to control access in AWS environments.
* Explore best practices for IAM implementation and cloud security.

#### 1.2 Use Case

IAM helps control who can access what in AWS by defining policies and assigning them to users, groups, or roles.


### 2. Project Tasks

#### 2.1 Part 1 - Policy and User Setup

1. Navigate to the **AWS Management Console** and locate **IAM** using the search bar.  
   ![initiate-policy-creation](images/clickiam.png)

2. On the IAM dashboard, select **Policies**. Search for **EC2**, choose **AmazonEC2FullAccess**, then click **Create policy**.  
   ![create-policy](images/createpolicy.png)

   * Select **All EC2 actions**, tick **All resources**, and click **Next**.  
     ![allec2actions](images/allec2actions.png)
   * Click **Create policy**.

3. Go to the **Users** section and select **Create user**.  
   ![create-user](images/createuser.png)

   * Enter a username, enable **AWS Management Console access**, set a password, and require the user to change it at next sign-in.  
     ![userdetails](images/specifyuserdetails.png)

   * Choose **Attach policies directly**, filter for **Customer managed policies**, and select the policy created earlier.  
     ![initiate-policy-creation](images/attachpolicytouser.png)

   * Click **Next** and then **Create user**.  
     ![initiate-policy-creation](images/usercreatedsuccessfully.png)


#### 2.2 Part 2 - Group and Role-Based Access

1. In the **User groups** section, create a group and name it (e.g., "Development-team").  
   ![create-user-group](images/createusergroup.png)  
   ![create-user-group](images/usergroupcreated.png)

2. Create a user named **Jack**, and during setup, choose **Add user to group**. Select the previously created group and proceed.  
   ![create-user-jack](images/userjackcreatedsuccessfully.png)  
   ![create-user-jack](images/addusertogroup.png)

3. Repeat the process for a new user named **Ade**, adding him to the same group.  
   ![create-user-ade](images/clickcreateuserade.png)  
   ![create-user-jack](images/addusertogroup.png)

4. Navigate to the **Policies** section and click **Create policy**.  

   * Select services **EC2** and **S3**.  
     ![ec2](images/allec2actions2.png)  
     ![s3](images/alls3actions2.png)

   * Name the policy (e.g., "development-policy") and click **Create policy**.  
     ![devteampolicy](images/clickcreatedevelopmentteampolicy.png)

5. Go to the **User groups** section, select **Development-team**, and go to the **Permissions** tab.  
   ![add-permission](images/Addpermissions.png)

   * Choose **Attach policy**, filter by **Customer Managed Policies**, and select the created **development-policy**.  
     ![attach-policy](images/attachpolicy.png)


### 3. Troubleshooting

If you can't sign in to your AWS account, verify that your credentials are correct and you're using the right sign-in method. For more help, refer to:  
[AWS Sign-In Troubleshooting Guide](https://docs.aws.amazon.com/signin/latest/userguide/troubleshooting-sign-in-issues.html)


### 4. Conclusion

This mini project successfully demonstrated the creation and management of IAM users, groups, and policies. It ensured secure access control and reinforced essential AWS IAM concepts for managing permissions within a cloud environment.
