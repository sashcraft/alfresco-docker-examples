# ACS 7.0 with Document Transformation Engine

This is an example of how to deploy ACS 7.0 with the DTE t-engine image.

This will use a DTE Standalone Server already deployed on an EC2 instance.

## Usage

You will need a working Docker and docker-compose environment.

1. Install [amazon-ecr-credential-helper](https://github.com/awslabs/amazon-ecr-credential-helper) and [configure](https://github.com/awslabs/amazon-ecr-credential-helper#configuration).
2. Log in to the Support AWS Console via Okta, selecting the OktaCustomer-SupportAdmin role.
3. Switch to N. Virginia (us-east-1) region and navigate to the EC2 console.
4. If you do not already have a "personal" security group for remote access (your external IP address), create one. Ensure you have an Inbound Rule for port 8080, and for port 3389 if you wish to RDP into the DTE Standalone Server. See SG sg-02a259558d60dc5ec for an example. Ensure you name/tag your SG with identifying information.
5. Locate the "Support DTE 2.3" EC2 instance. Add your security group to the instance.
6. Ensure you have the security group set up properly by attempting to access the [DTE console](http://alfrescodte23.ddns.net:8080/transformation-server/home). The credentials are alfresco/alfresco. If you are unable to access, double check your security group, or contact Scott Ashcraft for assistance.
7. Run `docker-compose up -d`

