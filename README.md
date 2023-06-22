Introduction:
    This user guide will explan how to onboard AWS Single and Multi Account(s) on Corestack.There are certain prerequisites that need to be set up in your AWS account before it can be onboarded into CoreStack. It primarily involves creating CUr Bucket, an IAM Role for assessment and enabling Cloudformation Stackset on Organization. 

    Onboarding AWS Single Account:
        
        * Login to the AWS account.
        * Navigate to CloudFormation.
        * Click Create Stack with new resources. 
        * Select Template is ready option in the Prepare template field.
        * Select Upload a Template file.
        * Select the Single account onboarding Cloudformation Template file.Click Next
        * Provide values for the Stack name and you can view additional fields that can be left with default values. Click Next
        * You can leave the values for the fields in this screen as default or make changes as necessary including assigning Tags, providing notification options, etc.Click Next.
        * The information provided in all the steps will be displayed. After reviewing the provided information for correctness, scroll down to the end of the screen and click on the _acknowledge _checkbox.
        * Click Create Stack.

The stack creation process will be initiated, and the status can be viewed.

    Navigate to Stack Info tab to see the overview of the stack and the final status.
    Click Refresh _icon to retrieve the updated status. When it is successfully completed, you will see the status as “_CREATE_COMPLETE”.
    Navigate to _Outputs _tab to view the access credentials (ARN).

Onboarding AWS Multiple Accounts:
            For AWS Bulk accounts onboarding, ther are few requirements must be verified
                a. CUR Buckets must be created under Billing Dashboard --> Cost & usage Reports.<br/>
                b. Cloudformation StackSet service must be enabled in AWS Organization ---> Services
    
    1. Onboard Master Account:
            * Login to the AWS Master account.
            * Navigate to CloudFormation.
            * Click Create Stack with new resources. 
            * Select Template is ready option in the Prepare template field.
            * Select Upoad a Template file.
            * Select the Multi account onboarding Cloudformation Template file.Click Next
            * Provide values for the CUR Bucket Name, Stack name and Role Name (Stack Name = Cloudelligent-Stack and RoleName = cloudelligent-assessment-role)you can view additional fields that can be left with default values. Click Next
            * You can leave the values for the fields in this screen as default or make changes as necessary including assigning Tags, providing notification options, etc.Click Next
            * The information provided in all the steps will be displayed. After reviewing the provided information for correctness, scroll down to the end of the screen and click on the _acknowledge _checkbox.
            * Click Create Stack.
    2. Onboard Bulk Accounts:
            * Navigate to CloudFormation.
            * Click Create StackSet with new resources. 
            * Select Template is ready option in the Prepare template field.
            * Select Upoad a Template file.
            * Select the Multi account onboarding Cloudformation Template file.Click Next
            * Provide values for the CUR Bucket Name, Stack name and Role Name (Stack Name = Cloudelligent-Stack and RoleName = cloudelligent-assessment-role)you can view additional fields that can be left with default values. Click Next
            * You can leave the values for the fields in this screen as default or make changes as necessary including assigning Tags, providing notification options, etc.Click Next
            * In SetDeployment Options TAB Select Deployment targets --> Deploy to Organization, Specify Only one Default Region(Us-East-1)
            * Change the Deployment Option to Parallel and Select Next
            * The information provided in all the steps will be displayed. After reviewing the provided information for correctness, scroll down to the end of the screen and click on the _acknowledge _checkbox.
            * Click Submit to Deploy the StackSet.
