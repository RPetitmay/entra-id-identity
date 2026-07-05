<p align="center">
<img src="https://i.imgur.com/BWIlArV.png" alt="Entra ID"/>
</p>

<h1>Entra ID — User Identities (SC-300 Lab 1)</h1>
Create and manage users and groups in Microsoft Entra ID, including dynamic membership and administrative units. Maps to SC-300 Domain 1 (Implement and manage user identities, 20–25%).<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Entra ID
- Microsoft 365 Developer Tenant (E5 / P2)
- Microsoft Entra admin center

<h2>Operating Systems Used</h2>

- Windows 11 (browser-based)

<h2>List of Prerequisites</h2>

- A free Microsoft 365 developer tenant with E5 licensing
- Global Administrator access

<h2>Configuration Steps</h2>
<ol>
  <li><strong>Create users</strong> — Identity &rarr; Users &rarr; New user; assign departments (Sales, Finance).</li>
  <li><strong>Create an assigned group</strong> — Groups &rarr; New group, add members manually.</li>
  <li><strong>Create a dynamic group</strong> — set membership type to Dynamic User with rule <code>(user.department -eq "Sales")</code>; confirm it auto-populates.</li>
  <li><strong>Create an administrative unit</strong> — add Finance users, then scope a role (e.g., User Administrator) to the AU.</li>
</ol>

<h2>Key Concepts Demonstrated</h2>

- Dynamic groups auto-include users by attribute rule.
- Administrative units limit an admin's scope to a subset of the directory.

<h2>Lessons Learned</h2>

- Use an AU + scoped role to delegate management of just one department; use a dynamic group to auto-include them.
