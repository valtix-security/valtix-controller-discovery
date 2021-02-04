# valtix-controller-discovery

This AWS CloudFormation template creates IAM roles for use with Valtix Controller.  This template creates two (2) IAM Roles:

- valtix-controller-discovery-role is a cross account IAM role used by Valtix Controller (read-only)
- valtix-cloudwatchevent-inventory-role that posts Cloud Trail updates to the Valtix Controller.

Note: This CFT is for use with Valtix COntroller Rel 2.5.

## How to use:

1. Download the valtixdiscoveryonly.yml template file and open CloudFormation in AWS console and upload the file and deploy the stack
1. Log into the required AWS Account using the AWS Management Console
1. Select the AWS region. Even though IAM is region independent, this template creates a CloudWatch Event Rule that requires a region
1. Enter the parameter values as required:
    Enter a Stack name. For example, valtix-resources.
    ExternalId - This value can be changed later in the IAM role, leave it to the default (123456789)
    RoleNamePrefix – Enter a prefix to be added to all of the IAM roles that are created. For example, prefix `valtix` would create an IAM role called valtix-controller-discovery-role. It is recommended that `valtix` is used as prefix so you can easily identify the roles that were created for Valtix in the IAM page.
    ValtixControllerAccount – Enter the information which was provided by Valtix at the time of onboarding. This is the AWS Account ID where the Valtix Controller operates. This account is owned and operated by Valtix.
1. Select the checkbox I acknowledge that AWS CloudFormation might create IAM resources with custom names, and then click Create Stack.
1. Check the Events and Outputs tab of the CloudFormation Stack details for the progress. Allow 2 to 3 minutes for successful completion. If an error is displayed, check the AWS message to verify that the user running the CloudFormation template has the required IAM permissions to run templates and create IAM roles.
  
