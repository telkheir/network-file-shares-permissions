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
          <ol><li>"Read-Access"  -  Group: 'Domain Users'  -  Permissions: 'Read'</li>
              <li>"No-Access"  - Group: 'Domain Admins'  -  Permissions: 'Read/Write'</li>
              <li>"Write-Access"  -  Group: 'Domain Users'  -  Permissions: 'Read/Write'</li>
              <li>"Accounting"  -  Group: N/A  -  Permissions: N/A</li>
          </ol>
      </li>
      <li><h3 id = "step_2">Accessing file shares as a normal user</h3>
      </li>
      <li><h3 id = "step_3">Creating a new security group and testing access</h3>
      </li>
    </ol>
