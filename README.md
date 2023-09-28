<h1>Network File Shares and Permissions (In Progress!)</h1>

This tutorial is another follow up to the <a href = "https://github.com/telkheir/implementing-active-directory">implementing Active Directory in Azure</a> tutorial.


<h2>Environments and Technologies Used</h2>
    <ul>
      <li>Microsoft Azure</li>
      <li>Virtual Machines (Azure)</li>
      <li>Remote Desktop</li>
      <li>Microsoft Active Directory</li>
    </ul>

<h2>Operating Systems Used</h2>
    <ul>
      <li>Windows 10</li>
    </ul>

<h2>Navigation</h2>
    <ol>
      <li><a href = "#step_1">Creating file shares with various permissions</a></li>
      <li><a href = "#step_2">Accessing file shares as a normal user</a></li>
      <li><a href = "#step_3">Creating a new security group and testing access</a></li>
    </ol>

<h2>Tutorial</h2>
    <ol>
      <li><h3 id = "step_1">Creating file shares with various permissions</h3>
          Use Remote Desktop to login to DC-1 as one of the admin accounts created in the previous <a href = "https://github.com/telkheir/implementing-active-directory">project</a>. We're going to create 4 folders in the C:\ drive and assign them to the following groups and permissions:
          <br><br>
          <table>
              <tr>
                  <th>Name</th>
                  <th>Group</th>
                  <th>Permissions</th>
              </tr>
              <tr>
                  <td>Read-Access</td>
                  <td>Domain Users</td>
                  <td>Read</td>
              </tr>
              <tr>
                  <td>Write-Access</td>
                  <td>Domain Users</td>
                  <td>Read/Write</td>
              </tr>
              <tr>
                  <td>No-Access</td>
                  <td>Domain Admins</td>
                  <td>Read/Write</td>
              </tr>
              <tr>
                  <td>Accounting</td>
                  <td>N/A</td>
                  <td>N/A</td>
              </tr>
          </table>
          To assign a file to a group, right click the file and go to Properties. Go to the Sharing tab and type the group name you want the file to be added to. Set the permmissions as needed, share the folder, and copy the file path. The video below shows the process of setting up the "No-Access" file share.
          <br><br>
          [video - creating and assigning groups and permissions to no-access file share]
          <br><br>
      </li>
      <li><h3 id = "step_2">Accessing file shares as a normal user</h3>
          Now we will use Remote Desktop to access the Client-1 VM as one of the normal users we created in the <a href = "https://github.com/telkheir/implementing-active-directory#step_5">last lab</a> to see which files we have access to and what types of changes can be made to them. To quickly navigate to the shared folder, type "\\dc-1" into the address bar of File Explorer.
          <br><br>
          [Image - naviagtion to file share]
          <br><br>
          The files we created in the previous step should be in this location, along with some other default folders that were created when we initially set up the domain controller.
          <br>
          --------->>>> Test each folders, create some supplemental text files and see what edits you can make to the folders
          [images]
          <br><br>
      </li>
      <li><h3 id = "step_3">Creating a new security group and testing access</h3>
          Return to the DC-1 virtual machine and open Active Directory Users and Computers. We will create a new organizational unit in our domain called "Security-Groups" and within it, a new group called "Accountants" (don't mix this group up with the "Accounting" file share we created in <a href = "step_1">step 1</a>!). 
          <br><br>
          [video - making both folder - org unit and group witin]
          <br><br>
          Returning to the "Accounting" file share we made in <a href = "step_1">step 1</a>, we can now place it in the "Accountants" domain group we just created and assign it "Read/Write" permissions.
          <br><br>
          [image - or vid idk whatevers cleanest]
          <br><br>
          After setting up these new rules for the "Accounting" file share, return to Client-1 and attempt to access the "Accounting" file share as a random user. You should not be allowed access because we have no users in the "Accountants" group we made. Now we will return to the DC-1 virtual machine and assign the user that's currently logged into Client-1 to the "Accountants" domain group, which should allow them access to the "Accounting" file share. Do this in Active Directory Users and Computers and double click the "Accountants" group. Go to Members, click "Add...", and input the username of the account currently logged into Client-1. Return to the Client-1 and test access once again. You may need to log out and back in again, but the user shoould now have access, read, and write permissions.
          <br><br>
          [video - accounting folder config]
      </li>
    </ol>
