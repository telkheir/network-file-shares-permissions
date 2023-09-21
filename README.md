<h1>Network File Shares and Permissions</h1>

Point of tutorial
This project was another follow up to the <a href = "https://github.com/telkheir/implementing-active-directory">implementing Active Directory in Azure</a> tutorial.


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
          <br><br>
          To assign a file to a group, right click the file and go to Properties. Go to the Sharing tab and type the group name you want the file to be added to. Set the permmissions as needed, share the folder, and copy the file path. The video below shows the process of setting up the "No-Access" file share.
          <br><br>
          [video - creating and assigning groups and permissions to no-access file share]
          <br><br>
      </li>
      <li><h3 id = "step_2">Accessing file shares as a normal user</h3>
          Now we will use Remote Desktop to access the Client-1 VM as one of the <a href = "https://github.com/telkheir/implementing-active-directory#step_5">normal users we created in the last lab.</a>
      </li>
      <li><h3 id = "step_3">Creating a new security group and testing access</h3>
      </li>
    </ol>
