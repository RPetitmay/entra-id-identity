<p align="center">
<img src="https://i.imgur.com/REPLACE_WITH_YOUR_BANNER.png" alt="Microsoft Entra ID Logo"/>
</p>
<h1>Entra ID Identity Lab</h1>
This tutorial outlines the configuration and validation of core <strong>identity and access management</strong> in Microsoft Entra ID. It covers creating and managing users and groups, dynamic group membership, self-service password reset (SSPR), and a baseline Conditional Access policy — the foundational tasks of an Identity &amp; Access Administrator.<br />
<h2>Environments and Technologies Used</h2>

Microsoft Entra ID (formerly Azure Active Directory)
Microsoft 365 Developer Tenant (E5 / Entra ID P2 licensing)
Microsoft Entra admin center (portal)
Notepad/Notes App (for saving usernames, passwords, and object IDs)


<h2>Operating Systems Used</h2>

Windows 11


<h2>List of Prerequisites</h2>

A Microsoft 365 developer tenant (free) with E5 licensing enabled
Global Administrator access to the tenant
Basic understanding of identity concepts (users, groups, roles)


<h2>Configuration Steps</h2>
<h3>1. Create and Manage Users</h3>
<ol>
  <li>Sign in to the <strong>Microsoft Entra admin center</strong>.</li>
  <li>Go to <strong>Identity &gt; Users &gt; All users &gt; New user &gt; Create new user</strong>.</li>
  <li>Create several test users, assigning a department (e.g., Sales, Finance) to each.</li>
  <li>Verify the users appear in the directory and can be assigned licenses.</li>
</ol>
<p align="center">
<img src="https://i.imgur.com/REPLACE_WITH_SCREENSHOT.png" height="80%" width="80%" alt="Create user"/>
</p>
<h3>2. Create Groups (Assigned and Dynamic)</h3>
<ol>
  <li>Go to <strong>Identity &gt; Groups &gt; All groups &gt; New group</strong>.</li>
  <li>Create a <strong>security group</strong> with <strong>Assigned</strong> membership and add users manually.</li>
  <li>Create a second security group with <strong>Dynamic User</strong> membership.</li>
  <li>Set the membership rule, e.g. <code>(user.department -eq "Sales")</code>.</li>
  <li>Confirm the dynamic group auto-populates with matching users (may take a few minutes).</li>
</ol>
<h3>3. Configure Self-Service Password Reset (SSPR)</h3>
<ol>
  <li>Go to <strong>Protection &gt; Password reset &gt; Properties</strong>.</li>
  <li>Enable SSPR for a selected group.</li>
  <li>Under <strong>Authentication methods</strong>, set the number of methods required and available options.</li>
  <li>Test the flow at <strong>aka.ms/sspr</strong> with a test user.</li>
</ol>
<h3>4. Create a Baseline Conditional Access Policy</h3>
<ol>
  <li>Go to <strong>Protection &gt; Conditional Access &gt; Policies &gt; New policy</strong>.</li>
  <li>Target a test group of users and all cloud apps.</li>
  <li>Under <strong>Grant</strong>, require multifactor authentication.</li>
  <li>Set the policy to <strong>Report-only</strong> first, then review sign-in log impact before enforcing.</li>
  <li>Always exclude a break-glass (emergency access) account from the policy.</li>
</ol>
<h3>5. Validate</h3>
<ol>
  <li>Sign in as a test user and confirm the expected MFA prompt or SSPR behavior.</li>
  <li>Open <strong>Monitoring &gt; Sign-in logs</strong> and review the <strong>Conditional Access</strong> tab to confirm which policy applied.</li>
</ol>
<h2>Key Concepts Demonstrated</h2>

<strong>Dynamic groups</strong> assign membership by attribute rule rather than manual adds.
<strong>SSPR</strong> reduces helpdesk load and is a core identity self-service feature.
<strong>Conditional Access</strong> enforces access controls based on signals; report-only mode lets you test safely, and break-glass accounts are always excluded.


<h2>Lessons Learned</h2>

Report-only Conditional Access prevents accidental lockouts while you validate impact.
Excluding a break-glass account is a non-negotiable safeguard in any identity deployment.
Dynamic membership keeps group access accurate as user attributes change.
