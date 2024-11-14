# Installation and Configuration of Active Directory Domain Services (AD DS) on Windows Server 2012 R2

<details>
  <summary><h2>Challenge</h2></summary>
  
Install and configure the Active Directory server using the virtual machine you used for the DNS and DHCP tasks.

- 1- Install the AD DS role on Windows Server 2012 R2
- 2- Create a domain `wilders.lan`
- 3- Document the procedure you used so it can be reproduced and posted as the solution for this task.
</details>

<details>
  <summary><h2>Prerequisites</h2></summary>

- 1- A pre-configured Windows Server 2012 R2 virtual machine.
- 2- DNS and DHCP roles must already be installed and configured.
- 3- Administrator access to the server.

</details>

<details>
  <summary><h2>Installation Steps</h2></summary>

**1. Open the Server Manager**  

- 1- Log in to your Windows Server 2012 R2.
- 2- Open the **Server Manager**.

**2. Add the AD DS Role**

- 1- In **Server Manager**, click **Manage** in the top right, then **Add Roles and Features**.
- 2- In the Add Roles and Features Wizard, click **Next** until you reach the **Installation Type** step.
- 3- Select **Role-based or feature-based installation** and click **Next**.
- 4- Select the local server (your server’s name) and click **Next**.
- 5- In the list of roles, check **Active Directory Domain Services (AD DS)**.
- 6- A window will appear to indicate additional features are required. Click **Add Features**.
- 7- Click **Next** until you reach the **Confirmation** step, then click **Install**.

**3. Promote the Server to Domain Controller**

Once the AD DS role is installed, a notification will appear in **Server Manager** to finalize the configuration.

- 1- Click the notification that says **Promote this server to a domain controller**.
- 2- In the Active Directory Configuration Wizard, select **Add a new forest** since this is a new domain.
- 3- In the **Root domain name** field, enter the desired domain name: `wilders.lan`.
- 4- Click **Next**.

**4. Configure Domain Options**

- 1- Choose the functional level for the forest and the domain. For Windows Server 2012 R2, leave **Windows Server 2012 R2** selected.
- 2- Check **DNS Server** to install the DNS role if necessary.
- 3- Enter a password for **Directory Services Restore Mode** (DSRM). Make sure to note it down in a safe place.
- 4- Click **Next**.

**5. DNS Configuration**

- 1- If a warning about DNS delegation appears, click **Next** to continue.
- 2- Verify the NetBIOS name settings (it should automatically be configured based on your domain).
- 3- Click **Next**.

**6- Paths for Directories**

- 1- Leave the default paths for **Database**, **Log files**, and **SYSVOL**.
- 2- Click **Next**.

**7. Verify the Configuration**

- 1- On the **Options** screen, verify that all configurations are correct.
- 2- Click **Next** to continue, then **Install** to start the installation.  
    **Note: The server will automatically restart once the installation is complete.**

**8. Verify the Installation**

- 1- After the restart, log in using the `wilders.lan` domain credentials.
- 2- Open **Server Manager** to verify that the AD DS and DNS roles are installed and functioning correctly.

</details>

<details>
  <summary><h2>Post-Installation Tests</h2></summary>
  
- 1- Open **Active Directory Users and Computers** from the **Tools** menu in Server Manager.
- 2- Verify that the `wilders.lan` domain is visible and accessible.
- 3- Create a new user to validate the configuration:
  - Right-click on **Users > New User**.
  - Fill in the required information and create the user.
- 4- Ensure that the newly created user can log in to the domain.

</details>

_This documentation allows reproducing the installation and configuration of Active Directory on a Windows Server 2012 R2 virtual machine with the `wilders.lan` domain._
