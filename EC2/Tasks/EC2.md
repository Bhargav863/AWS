# AWS EC2 Tasks

- **1.** Launch a Linux-1 EC2 instance and go through all the options while launching the EC2 instance.

- **2.** Launch a Windows EC2 instance with **Termination Protection** enabled.

- **3.** Launch another Linux-2 EC2 instance with **Stop Protection** enabled.

- **4.** Stop the Linux-2 EC2 instance. If it does not stop, disable Stop Protection and stop the instance.

- **5.** Stop the EC2 instance and check its status.

- **6.** Start the EC2 instance and check its status.

- **7.** Reboot the EC2 instance and check its status.  
  - What happens to the instance state?

- **8.** Terminate the EC2 instances.

- **9.** If you are unable to terminate an EC2 instance, disable Termination Protection:
  - Instance Settings → Change Termination Protection → Uncheck **Enable**.

- **10.** Launch a Linux-3 EC2 instance with **Termination Protection** enabled and try to stop it.
  - Check whether the instance stops even though Termination Protection is enabled.

- **11.** Launch a Linux-4 EC2 instance with **Stop Protection** enabled and try to terminate it.
  - Check what happens when you try to terminate an instance with Stop Protection enabled.

- **12.** Create a Launch Template from the Linux instance and launch an EC2 instance using the template.

- **13.** Review all the options available under **Actions**.

- **14.** Make sure all EC2 instances are terminated.
  - Go to the EC2 Dashboard.
  - Verify that everything is **0** except the **Key Pairs** and **Security Groups**.

- **15.** Connect to the Linux machine using the terminal.
  - Open Command Prompt.
  - Navigate to the location where the `.pem` file is stored.
  - Copy and run the connection command from:
    - Instance → Connect → SSH Client.

- **16.** Try to stop, start, and reboot the EC2 instance.
  - Check whether the **Public IP** changes or not.
  - Reboot the EC2 instance and check its **Instance State**.
  - Reboot the EC2 instance and check whether the **Public IP** changes or not.
  - Stop and start the EC2 instance and check whether the **Private IP** changes or not.

- **17.** Assign an **Elastic IP (EIP)** to the EC2 instance.
  - Stop and start the instance.
  - Check whether the EIP changes or not.

- **18.** Disassociate the EIP from the instance and release it to AWS.

- **19.** Create a Linux Launch Template.
  - Launch EC2 instances from the template.
  - Delete the Launch Template.

- **20.** Launch an EC2 instance using the **Launch More Like This** option.

- **21.** Review all the options available under **Actions**.

- **22.** Launch a Windows EC2 instance with **Shutdown Behavior = Terminate**.
  - Log in to the Windows EC2 instance.
  - Shut down the Windows EC2 instance.
  - Check what happens to the instance.

- **23.** Reboot the Windows EC2 instance.
  - Immediately go to **Instance Screenshot**.
  - Check what the screenshot shows.

- **24.** Enable **SSH access from anywhere**.

- **25.** Launch an **Amazon Linux 2023** EC2 instance and connect to it using **EC2 Instance Connect**.

- **26.** Terminate all EC2 instances.
  - If Termination Protection is enabled, disable it first:
    - Instance Settings → Change Termination Protection → Uncheck **Enable**.

- **27.** Delete the Launch Template.

- **28.** Check the EC2 Dashboard.
  - Everything should be **0** except **Key Pairs** and **Security Groups**.
