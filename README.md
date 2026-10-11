<h1>Traffic Analysis Exercise: Easy as 123</h1>
<a href = "https://www.malware-traffic-analysis.net/index.html ">Source of the Activity</a>

<h2>Objective</h2>
<ul>
  <li>What is the IP address of the infected Windows client?</li>
  <li>What is the MAC address of the infected Windows client?</li>
  <li>What is the host name of the infected Windows client?</li>
  <li>What is the user account name from the infected Windows client?</li>
  <li>What is the full name of the user from the user account?</li>
</ul>

<h2>Tool</h2>
<ul>
  <li>Wireshark</li>
</ul>

<h2>Instructions</h2>
<!--Dito yung image nung instructions-->

<h2>Step-by-step Answer</h2>
<h3>Step 1: Finding the IP of the infected</h3>
<p>Go to Statistics then Conversation. Due to the irregular amount of data being transferred from 10.2.28.88 and the transactions being over TCP, we can suspect that this is the infected device.</p>
<!--Insert the 2 photo for step 1-->

<h3>Step 2: Finding the MAC address of the infected</h3>
<p>Using nbns filter to look for more details regarding the infected IP, we can find the MAC address as the source. In Wireshark, NBNS stands for NetBIOS Name Service, a legacy protocol used to map computer names to IP addresses on a local network.</p>
<!--Image for step 2-->

<h3>Step 3: Finding the user account name of the infected</h3>
<p>Using the Kerberos.CNameString to find the hostame. This filter is used in Wireshark to find user account names because it maps to the Client Name (CName) field inside Kerberos authentication request packets (AS-REQ), which explicitly contains the plaintext username attempting to log into an Active Directory domain.</p>

<h3>Step 4: Finding the Hostname of the infected</h3>
<p>Using the Kerberos.CNameString, we can also find the Hostname of the Windows client.</p>

<h3>Step 5: Finding the Full Name of the user</h3>
<p>Since we have found that the username is brolf, we can make a guess. Using that info, we can try some name to search. In the screenshot, I used ‘Rolf’ as the string to search inside the packets.</p>

<h2>Answer</h2>
<p>IP Address: <strong>10.2.28.88</strong></p>
<p>MAC Address: <strong>Intel_b2:4d:ad</strong></p>
<p>User account name: <strong>brolf</strong></p>
<p>Name of the user: <strong>Becka Rolf</strong></p>
<p>Hostname of Windows client: <strong>DESKTOP-TEYQ2NR</strong></p>

<h2>What I have learned :bulb:</h2>
<ul>
  <li>How to analyze packets and frames to look for device information.</li>
  <li>Being more comfortable at navigating Wireshark</li>
  <li>How to better use filters to search for specific information</li>
</ul>
