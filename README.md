# football.space
Backend application

Since you are running on an EC2 instance, you are most likely running Amazon Linux 2023 or Amazon Linux 2. We will use Node Version Manager (NVM) to safely install Node.js.
Run these exact commands one by one in your terminal:
Step 1: Install NVM (Node Version Manager)
Bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash
Step 2: Activate NVM in Your Current Terminal Session
Bash
. ~/.nvm/nvm.sh
Step 3: Install Node.js (Version 18 or higher is required for Amplify)
Bash
nvm install 20
Step 4: Verify the Installations Work
Now check if the system can see the tools:
Bash
node -v
npm -v
(Both should output version numbers now, like v20.x.x and 10.x.x)
🏁 Pick Up Where You Left Off
Now that the system libraries are installed, you can execute the previous plan inside your traineffective-backend folder:
Bash
# 1. Now this command will run flawlessly
npm init -y

# 2. Scaffold your Amplify infrastructure files
npm create amplify@latest -- --yes
Run the NVM installation commands above to unblock npm. Let me know if npm -v spits out a version number successfully! You're handling this cloud interface like a pro.


====

Role for Amplify
For premium quality with zero human resource overhead, we do not pass hard-coded Secret Access Keys onto our servers. Doing that is a major security vulnerability. Instead, we use a native AWS feature called an IAM Instance Profile (EC2 Role).
Open your local web browser and log into your AWS Management Console.
Search for IAM in the top search bar and click on Roles -> Create role.
Select AWS service as the trusted entity type, and choose EC2 from the service dropdown. Click Next.
In the permissions search bar, look for AdministratorAccess or PowerUserAccess, check the box next to it, and click Next.
Name the role EC2-Amplify-Admin-Role and click Create role.
Go to your EC2 Dashboard, check the box next to your instance (ip-172-31-2-17), click Actions -> Security -> Modify IAM role.
Select your newly created EC2-Amplify-Admin-Role from the dropdown and hit Update IAM role.


======
