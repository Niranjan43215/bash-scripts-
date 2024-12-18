# bash-scripting 
1. Replace Variables:

Replace <YOUR_ACR_NAME> with your Azure Container Registry name.
Replace <YOUR_RG_NAME> with your Resource Group name.

2. Azure CLI Login:

Ensure you are logged in to Azure CLI (az login).

3. Make Script Executable: Run the following command:

chmod +x acr_image_cleanup.sh

4. Test the Script: Execute the script:

./acr_image_cleanup.sh

5.Automate with Cron Job:

Run crontab -e to edit the cron jobs.
Add the following line to schedule the script to run daily at midnight:

0 0 * * * /path/to/acr_image_cleanup.sh >> /path/to/acr_cleanup.log 2>&1

####################################################################################################################################

**Azure Container Registry (ACR) Image Cleanup Script**
This Bash script automates the cleanup of old container images in an Azure Container Registry (ACR). It ensures that only the latest 5 images are retained for each repository and deletes all older images.

**How It Works**
Fetch All Repositories
The script retrieves a list of all repositories in the specified ACR.

**Fetch Image Tags**
For each repository, it fetches all image tags and sorts them in descending order based on their creation time.

**Retain Latest 5 Tags**
Only the latest 5 image tags are retained for each repository.

**Delete Old Images**
Images older than the latest 5 are deleted using the Azure CLI.

**Scheduled Automation**
You can schedule this script to run daily using a cron job.

**Pre-requisites**
Azure CLI: Make sure the Azure CLI is installed and configured on the system.
Install Azure CLI: Azure CLI Installation Guide
Permissions: The user or service principal running the script must have the Contributor or AcrPush role for the Azure Container Registry.
Azure Login: Ensure the user is logged in using az login.
