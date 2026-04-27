Building an EC2 instance in AWS

Open your web browser and visit the AWS console website: https://aws.amazon.com/console/.

In the upper right corner, click Sign in to Console.

On the next screen, enter your Account ID, IAM username, and Password into each of the indicated fields.  Click Sign in.

In the Console Home screen, click inside the Search bar at the top of the screen and search for EC2.  Click on the EC2 link that comes up.  

Creating a security group for the EC2 instance:

    In the EC2 window, look for the Network & Security section on the left side of the screen and click Security Groups.

    In the Security Groups section, click the orange button named Create security group. 

        Perform the following actions in the Create security group window: 
            In the Basic details section, enter the name of the security group in the Security group name field.  As best practice, please do not add any spaces to the name and append -sg to the end of the name to indicate that it is a security group.
            
            Enter a brief description of the security groups purpose in the Description field. For simplicity, this can be the same as the security group name.
            
            Leave the VPC as default. 

            In the Inbound rules section, click the Add rule button.
            
            Click the Type dropdown field and change it to HTTP.  The Protocol should change to TCP and the Port range should change to 80.
            
            Click the Source type dropdown field and change it to Anywhere-IPv4.  The Source should change to 0.0.0.0/0.  
            
            In the Description field, add a brief description of the the purpose of the Inbound rule.  

            Skip the Outbound rules section.  

            In the Tags - optional section, you can add key value pairs to describe the security group.  This is optional but can be useful for organizational purposes.
            
            Click the Add new tag button and add the name of the tag in the Key field.  Next, add a descriptor for the tag.

            Finally, click the orange Create security group button.

    If the process was successful, you should see a green banner at the top of the page.

Creating the EC2 instance:

    On the left side of the screen, in the Instances section, click Instances.

    In the Instances section, click the orange button named Launch instances.

        Perform the following actions in the Launch an instance window: 
            In the Name and tags section, enter the name of the instance.  
            
            In the Application and OS Images section (Amazon Machine Image), leave everything as default. Collapse the section by clicking the down triangle (chevron) next to the section name.
            
            In the Instance type section, leave everything as default. Collapse the section by clicking the down triangle (chevron) next to the section name.  
            
            In the Key pair (login) section, click on the Key pair name - required dropdown field and select the default Proceed without a key pair (Not recommended).  
            
            In the Network settings section, change the Firewall (security groups) section by clicking the Select existing security group choice.  
            
            In the Common security groups section, click the dropdown and select the security group you just created previously.  
            
            In the Configure storage section, leave everything as default. Collapse the section by clicking the down triangle (chevron) next to the section name.
            
            Expand the Advanced details section by clicking the down triangle (chevron) next to the section name.  Scroll to the bottom of the section until you reach User data - optional.  Paste the start-up script for the web page into this field.  

            Finally, click the orange Launch instance button.

    On the left side of the screen, in the Instances section, click Instances.  In the Instances section, you should see your new instance with a green Instance state of Running.

    Click the checkbox next to the Instance name.  This will populate information about the instance in the section below it.  

    In this details section, look for the Public DNS section and click the overlapping squares icon to copy the website URL.  

    Open a new browser tab and type http:// and paste the URL after it.  The webpage should resolve successfully if you built the instance correctly.  

Teardown of the EC2 instance and its Security Group: 

    If you are not in the Instances section of the EC2 page, click on Instances to go there now. 

    In the Instances section, click the checkbox next to the Instance name of the instance you want to teardown.

    Click the Instance state dropdown button and select Terminate (delete) instance.  

    A new Terminate (delete) instance window should launch.  Verify that the instance you want to delete is currently showing in the Instance ID section.  Once verified, click the orange Terminate (delete) button.  

    A green banner should appear at the top of the screen if you were successful.  The Instance state should first show Shutting down and then after a minute or so, it will show Terminated.  

    In the EC2 window, look for the Network & Security section on the left side of the screen and click Security Groups.  

    Click the checkbox next to the name of the security group you want to teardown.  Be mindful to NEVER select the default security group as it will cause massive issues.  

    Click the Actions button and select Delete security groups.  

    A new Delete security groups window should launch.  Verify that the security group you want to delete is currently showing in the window.  Once verified, click the orange Delete button.  Refresh the AWS console webpage and the security group should now be deleted.  

    You have now successfully completed the teardown.  











