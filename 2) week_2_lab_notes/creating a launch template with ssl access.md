Log into AWS console

Create a security group with SSH and HTTP access.

Create an EC2 instance using the security group you just created.  Verify its functionality.

Select the instance's checkbox -> select Actions -> Images and templates -> Create template from instance.

Enter a name for the template.

Enter a description for the template.

Verify that the settings match the original instance settings. 

Click Create launch template. 

Verify integrity of the launch template by creating an instance with it.  

Select the launch template checkbox -> Actions -> Launch instance from template.

Verify that the instance settings match the template. If you have created additional versions of the template, select the one you want to base the instance on.  

Rename the instance in the tags section if you want.

Click Launch instance.  

Verify that the instance has passed its checks and the website launches successfully.

Verify SSH capability by selecting the checkbox of the instance and clicking Connect. 

Keep the default settings and click Connect again. 

A new window should open and the OS you based the instance on should launch.  Ping 8.8.8.8 for your sanity and rejoice if it works.  



