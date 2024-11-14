# Creating an Organizational Unit, User Group, and User in Active Directory for `wilders.lan`

After setting up Active Directory with the `wilders.lan` domain, follow these steps to create an Organizational Unit (OU), a user group, and add a user to that group.

<details>
  <summary><h2>Objective</h2></summary>

1. Create an Organizational Unit named **Wilders_students**.
2. Create a user group named **Students** within this OU.
3. Create a user within this group.
</details>

<details>
  <summary><h2>Prerequisites</h2></summary>

- Administrator access to Active Directory with the `wilders.lan` domain.
</details>

<details>
  <summary><h2>Procedure Steps</h2></summary>

### 1. Create the Organizational Unit (OU)

1. Open **Active Directory Users and Computers** from the **Tools** menu in **Server Manager**.
2. In the console, right-click on the `wilders.lan` domain name, then select **New > Organizational Unit**.
3. Name the new OU **Wilders_students**.
4. Check the **Protect object from accidental deletion** option to secure the OU.
5. Click **OK** to create the OU.

### 2. Create the User Group

1. In the **Wilders_students** OU, right-click and select **New > Group**.
2. Name the group **Students**.
3. Leave the default options for **Group type** (Security) and **Group scope** (Global).
4. Click **OK** to create the group.

### 3. Create a User in the Group

1. In the **Wilders_students** OU, right-click and select **New > User**.
2. Enter the user information:
   - **First Name**: John
   - **Last Name**: Doe
   - **User logon name**: jdoe
3. Click **Next** and set the user’s password.
4. Uncheck **User must change password at next logon** if you want the password to be permanent.
5. Click **Next** and then **Finish** to create the user.

### 4. Add the User to the Students Group

1. Right-click on the user **John Doe** (or the username you created) in the **Wilders_students** OU, then select **Properties**.
2. Go to the **Member Of** tab and click **Add**.
3. Enter **Students** in the search field, then click **Check Names** to confirm.
4. Click **OK** to add the user to the **Students** group.

</details>

<details>
  <summary><h2>Verification</h2></summary>

- Open **Active Directory Users and Computers** and verify that:
  - The **Wilders_students** OU exists in the `wilders.lan` domain.
  - The **Students** group is present within the **Wilders_students** OU.
  - The user **John Doe** is a member of the **Students** group.

</details>

_This documentation allows reproducing the creation of an Organizational Unit, a user group, and a user in Active Directory for the `wilders.lan` domain._
