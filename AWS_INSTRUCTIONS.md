# AWS CI/CD Pipeline Setup Instructions

## 1. Get AWS IAM Credentials
To allow GitHub Actions to push to ECR and deploy to EC2, you need an IAM user with appropriate permissions.

1.  Log in to the [AWS Management Console](https://console.aws.amazon.com/).
2.  Search for **IAM** in the top search bar and click it.
3.  In the left sidebar, click **Users**, then click **Create user**.
4.  **User name**: `github-cicd-user`. Click **Next**.
5.  **Permissions options**: Select **Attach policies directly**.
6.  Search for and select the following policies:
    *   `AmazonEC2ContainerRegistryFullAccess` (to push Docker images)
    *   `AmazonEC2FullAccess` (to manage/access EC2)
    *   `IAMFullAccess` (Optional, but helps if you want to automate more. Better to use a specific policy if you're security-conscious).
    *   *Note: For a production environment, use more restrictive policies.*
7.  Click **Next**, then **Create user**.
8.  Click on the newly created user `github-cicd-user`.
9.  Go to the **Security credentials** tab.
10. Scroll down to **Access keys** and click **Create access key**.
11. Select **Command Line Interface (CLI)**, check the box for "I understand...", and click **Next**.
12. (Optional) Set a description and click **Create access key**.
13. **IMPORTANT**: Copy the **Access key ID** and **Secret access key**. You will need these for GitHub Secrets.

## 2. Prepare AWS Resources
You will need an ECR repository and an EC2 instance. I can provide the commands to create these once you provide the credentials, or you can create them manually:
*   **ECR Repo Name**: `my-app-repo`
*   **EC2 Instance**: Linux (Ubuntu 22.04 recommended) with Docker installed.

Please provide the **Access Key ID**, **Secret Access Key**, and your preferred **AWS Region** (e.g., `us-east-1`) when you have them.
