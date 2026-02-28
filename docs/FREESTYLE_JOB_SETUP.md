# Jenkins UI Configuration Guide for Creating Freestyle Jobs

## Introduction
This guide provides detailed steps on how to set up Jenkins freestyle jobs using the Jenkins UI, including configuring build steps, managing credentials, and integrating with GitHub using webhooks.

## Creating a Freestyle Job
1. Navigate to your Jenkins dashboard.
2. Click on **New Item**.
3. Enter a name for your job and select **Freestyle project**.
4. Click **OK** to create the job configuration.

## Configuring Build Steps
1. In the job configuration page, scroll down to the **Build** section.
2. Click on **Add build step** and choose the type of build step (e.g., **Execute Shell**, **Invoke Ant**, etc.).
3. Configure the specific settings for the selected build step as needed.

## Setting Up Credentials
1. Go to **Manage Jenkins**.
2. Select **Manage Credentials** and choose the appropriate domain.
3. Click on **Add Credentials** to create a new credential.
   - Fill in the required fields such as Kind, Scope, ID, Username, and Password/Secret.
4. Save the credentials.
5. In your freestyle job configuration, under the build step, select the credentials from the dropdown where necessary.

## Integrating with GitHub Webhook
1. Go to your GitHub repository.
2. Click on **Settings**, then select the **Webhooks** option.
3. Click on **Add webhook**.
   - Payload URL: `http://<YOUR_JENKINS_URL>/github-webhook/`
   - Content type: `application/json`
   - Select **Just the push event** or any other events you want to listen to.
4. Click **Add webhook**.

5. In your Jenkins job, scroll down to the **Build Triggers** section.
6. Check the **GitHub hook trigger for GITScm polling** option.

## Testing the Configuration
1. Make a commit to your GitHub repository to trigger the webhook.
2. Check the Jenkins job to ensure it runs successfully.

## Conclusion
By following this guide, you should now have a Jenkins freestyle job set up with build steps, credentials, and GitHub webhook integration. This configuration allows for automated builds triggered by events in your GitHub repository.