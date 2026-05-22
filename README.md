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

=> nvm source string already in /home/ec2-user/.bashrc
=> bash_completion source string already in /home/ec2-user/.bashrc
=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
[ec2-user@ip-172-31-41-91 traineffective-backend]$ 

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

    37   npx ampx sandbox -final setup of amplify -if any issue follow below and try again
   38  export AWS_REGION="ap-south-1"
   40  npx cdk bootstrap aws://906034468055/ap-south-1
   41 npx ampx sandbox
   41  



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
