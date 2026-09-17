## 3.3. Product Backlog

<table>
	<thead>
		<tr>
			<th>Order</th>
			<th>US ID</th>
			<th>Title</th>
			<th>Description</th>
			<th>Story Points</th>
		</tr>
	</thead>
	<tbody>
      <tr>
       <td>1</td>
       <td>US01</td>
       <td>Optimization of Critical Asset Surveillance</td>
       <td>As a: Quality Lead / Researcher. I want to: Consult real-time monitoring capabilities and system alert protocols. So that: I can ensure the laboratory has the necessary tools to maintain sample integrity and comply with biosafety standards.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>2</td>
       <td>US02</td>
       <td>Selection of Capabilities Based on Asset Volume</td>
       <td>As a: Laboratory Administrator. I want to: Evaluate and select a subscription plan based on the number of sensors and storage units. So that: I can ensure the software infrastructure supports my laboratory's operational scale without monitoring interruptions.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>3</td>
       <td>US03</td>
       <td>Technical Validation and Information Request</td>
       <td>As a: Laboratory Manager. I want to: Submit a contact request detailing the specific needs of my cold chain. So that: I can receive personalized technical advice validating the compatibility of SafeLab sensors with my biological assets.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>4</td>
       <td>US04</td>
       <td>Secure Access to the Monitoring Ecosystem</td>
       <td>As a: Registered User (Technician/Admin). I want to: Authenticate through the secure access portal using IAM-managed credentials. So that: I can enter the Dashboard and manage thermal incidents according to my assigned permissions.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>5</td>
       <td>US40</td>
       <td>User Logout</td>
       <td>As a user, I want to log out to protect access to the platform.</td>
       <td>1</td>
    </tr>
    <tr>
       <td>6</td>
       <td>US41</td>
       <td>Session Persistence</td>
       <td>As a user, I want to keep my session active so I don't have to log in constantly.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>7</td>
       <td>US31</td>
       <td>Identity Hardening via Two-Factor Authentication (2FA)</td>
       <td>As a: System Administrator / Senior Lab Manager. I want to: Enable two-factor authentication (2FA) for my SafeLab account. So that: I can add an extra security layer protecting sensitive research data access against unauthorized attempts.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>8</td>
       <td>US43</td>
       <td>Single Sign-On (SSO) Integration via SAML/OAuth2</td>
       <td>As a: Corporate IT Security Manager. I want to: Integrate SafeLab login with corporate identity providers (Azure AD, Okta, Google Workspace) via SAML 2.0 / OAuth2. So that: Employees use corporate credentials for centralized access control.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>9</td>
       <td>US42</td>
       <td>Role-Based Access Control (RBAC) Management</td>
       <td>As a: System Administrator. I want to: Define custom user roles and assign granular permissions (e.g., Read-Only, Technician, QA Lead, Admin). So that: Operational security adheres to the principle of least privilege.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>10</td>
       <td>US46</td>
       <td>User Password Policy Enforcement and Expiration</td>
       <td>As a: IT Compliance Specialist. I want to: Enforce password complexity rules (12+ chars, symbols, numbers) and 90-day password rotation policies. So that: Account credentials satisfy corporate cybersecurity standards.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>11</td>
       <td>US20</td>
       <td>Monitoring Environment Initialization (Create Lab)</td>
       <td>As a: Laboratory Administrator. I want to: Register a new laboratory by setting up its technical parameters and security policies from the start. So that: I can establish a monitoring infrastructure that complies with specific standards for the samples stored.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>12</td>
       <td>US13</td>
       <td>Technical Registration and Sensor Linking</td>
       <td>As a: Laboratory Technician. I want to: Register and link new sensors to specific storage units (Racks/Refrigerators). So that: I can expand the monitoring network and ensure each biological asset has a properly assigned sensor.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>13</td>
       <td>US33</td>
       <td>Laboratory Search</td>
       <td>As a user, I want to search for laboratories by name to find them quickly.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>14</td>
       <td>US11</td>
       <td>Prioritized Management of Sites and Laboratories</td>
       <td>As a: Laboratory Coordinator. I want to: View the list of laboratories with advanced filters by criticality status and location. So that: I can immediately identify which sites present thermal anomalies and prioritize supervision at highest risk points.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>15</td>
       <td>US12</td>
       <td>Operational Management and Control of Storage Units</td>
       <td>As a: Laboratory Coordinator. I want to: Access the detailed control panel of a specific laboratory to manage its storage units and sensors. So that: I can execute operational decisions such as adjusting threshold parameters or preventive maintenance of cold units.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>16</td>
       <td>US21</td>
       <td>Technical and Regulatory Parameter Updates</td>
       <td>As a: Laboratory Coordinator. I want to: Modify technical configuration and safety parameters of a laboratory. So that: I can adapt monitoring to new biosafety protocols or physical infrastructure changes at the site.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>17</td>
       <td>US05</td>
       <td>Real-Time Thermal Monitoring and Risk Detection</td>
       <td>As a: Laboratory Coordinator. I want to: View the thermal status of all storage units in real time and in a centralized manner. So that: I can immediately detect critical temperature deviations and prevent the degradation of reagents or biological samples.</td>
       <td>8</td>
    </tr>
    <tr>
       <td>18</td>
       <td>US24</td>
       <td>Automated Thermal Excursion Detection</td>
       <td>As an: Intelligent Monitoring System. I want to: Analyze real-time sensor readings against defined Safe Thresholds. So that: I can automatically identify thermal excursions and prevent the use of reagents or samples whose integrity has been compromised.</td>
       <td>8</td>
    </tr>
    <tr>
       <td>19</td>
       <td>US08</td>
       <td>Traceability of Recent Critical Alerts</td>
       <td>As a: Compliance Officer. I want to: Monitor the recent alert log triggered by the system on the Dashboard. So that: I can verify that each thermal risk event has clear traceability and complies with response times required by bioclinical regulations.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>20</td>
       <td>US09</td>
       <td>Rapid Alert Response from Dashboard</td>
       <td>As a: Laboratory Technician. I want to: Interact with recent alerts directly from the Dashboard panel. So that: I can initiate corrective actions immediately without navigating complex menus, reducing risk exposure time for samples.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>21</td>
       <td>US34</td>
       <td>Alert Filtering</td>
       <td>As a user, I want to filter alerts by different criteria to prioritize my needs.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>22</td>
       <td>US35</td>
       <td>Full Alert Details</td>
       <td>As a user, I want to view full details of an alert to understand the incident.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>23</td>
       <td>US17</td>
       <td>Critical Incident Management and Resolution</td>
       <td>As a: Laboratory Technician / Coordinator. I want to: Manage active alerts by executing and logging corrective actions. So that: I can mitigate the impact of thermal excursions and ensure the incident is resolved under biosafety protocols.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>24</td>
       <td>US18</td>
       <td>Incident Lifecycle Management and Closure</td>
       <td>As a: Laboratory Coordinator. I want to: Manage the status of critical alerts until their final closure. So that: I can maintain operational control of the incident and ensure thermal stability has been restored in the storage unit.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>25</td>
       <td>US27</td>
       <td>Mandatory Logging of Corrective Actions</td>
       <td>As a: Laboratory Technician. I want to: Formally document measures taken to resolve a thermal anomaly. So that: I can comply with traceability protocols and allow root cause analysis in the future.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>26</td>
       <td>US26</td>
       <td>Automatic Escalation of Unattended Incidents</td>
       <td>As an: Operations Manager. I want to: Have the system apply the Escalation Policy if a critical alert is not acknowledged within established time. So that: Higher hierarchy personnel intervene in high-risk situations that have not been managed in time.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>27</td>
       <td>US25</td>
       <td>Trend-Based Preventive Alert Generation</td>
       <td>As a: Laboratory Coordinator. I want to: Receive preventive notifications when temperature trends indicate proximity to the critical threshold. So that: I can execute mitigation actions before actual loss of biological material occurs.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>28</td>
       <td>US06</td>
       <td>Thermal Stability Analysis via Historical Trends</td>
       <td>As a: Quality Assurance Lead. I want to: Analyze the temperature trend chart for the last 24 hours. So that: I can identify unstable behavior patterns in cold storage equipment before a complete breakdown occurs.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>29</td>
       <td>US37</td>
       <td>Historical Trend Visualization</td>
       <td>As a user, I want to view event trends to analyze patterns.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>30</td>
       <td>US07</td>
       <td>Critical Point Identification via Heatmap</td>
       <td>As a: Maintenance Technician. I want to: View the heatmap of storage units distributed across the laboratory. So that: I can identify which specific zones or racks are experiencing higher thermal stress and prioritize physical inspection of those units.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>31</td>
       <td>US10</td>
       <td>Preventive Management Based on Environmental Metrics</td>
       <td>As a: Laboratory Coordinator. I want to: Analyze combined metrics (temperature, vibration, and humidity) to execute preventive actions on storage equipment. So that: I can mitigate risks before a critical failure occurs in the cold chain and ensure optimal conditions based on sample type.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>32</td>
       <td>US15</td>
       <td>Activation of Mitigation Systems and Automated Response</td>
       <td>As a: Laboratory Coordinator. I want to: Enable or disable mitigation systems (auxiliary ventilation/cooling) under technical validation rules. So that: I can react safely to a thermal excursion and stabilize the environment without compromising the integrity of other equipment.</td>
       <td>8</td>
    </tr>
    <tr>
       <td>33</td>
       <td>US14</td>
       <td>Health Monitoring and Device Calibration</td>
       <td>As a: Maintenance Lead. I want to: Check the battery status and last calibration date of each sensor. So that: I can schedule preventive technical services and avoid interruptions in critical data capture.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>34</td>
       <td>US29</td>
       <td>Execution and Logging of Sensor Calibration</td>
       <td>As a: Calibration Technician / Support. I want to: Execute sensor calibration process directly from configuration panel. So that: I can guarantee reading accuracy according to ISO 17025 standard and avoid legal deviations in temperature reports.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>35</td>
       <td>US19</td>
       <td>Regulatory Compliance Traceability and Audit</td>
       <td>As a: Quality Auditor. I want to: View detailed history of events, alerts, and actions executed in the system. So that: I can generate compliance reports for regulatory bodies (e.g., ISO, DIGEMID) and verify cold chain integrity over past periods.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>36</td>
       <td>US28</td>
       <td>Regulatory Audit Report Generation</td>
       <td>As a: Quality Director / External Auditor. I want to: Generate consolidated and immutable reports of all readings and incidents for a given period. So that: I can present evidence to regulatory entities (DIGEMID/ISO) certifying cold chain integrity.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>37</td>
       <td>US16</td>
       <td>Archiving and Custody of Laboratory History</td>
       <td>As a: Laboratory Administrator. I want to: Archive or decommission laboratories that are no longer operational. So that: I can maintain system organization without losing historical thermal data traceability required by audits.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>38</td>
       <td>US30</td>
       <td>Customization of Alert Channels and Activity Summaries</td>
       <td>As a: Laboratory Coordinator. I want to: Configure alert reception channels and frequency of activity reports. So that: I can optimize incident communication according to severity and avoid "alert fatigue" among duty personnel.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>39</td>
       <td>US36</td>
       <td>Email Notification Management</td>
       <td>As a user, I want to enable or disable email notifications to control how I receive laboratory alerts.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>40</td>
       <td>US39</td>
       <td>Real-Time System Notifications</td>
       <td>As a user, I want to receive visual notifications following important actions.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>41</td>
       <td>US49</td>
       <td>In-App System Maintenance and Outage Banners</td>
       <td>As a: System Administrator. I want to: Broadcast system-wide maintenance banners to active users. So that: Personnel are aware of scheduled software updates or temporary server maintenance windows.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>42</td>
       <td>US32</td>
       <td>Active Session Audit and Geographic Access Control</td>
       <td>As a: Security Officer. I want to: Monitor active sessions and login history (location and IP) of my account. So that: I can identify suspicious logins from unusual locations and revoke sessions that might compromise laboratory integrity.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>43</td>
       <td>US45</td>
       <td>Inactivity Session Auto-Lock and Timeout</td>
       <td>As a: Security Officer. I want to: Enforce an automatic session lock after 15 minutes of user inactivity. So that: Unattended terminals in shared laboratory spaces do not expose sensitive operational controls.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>44</td>
       <td>US38</td>
       <td>User Profile Editing</td>
       <td>As a user, I want to edit my personal information to keep my data updated.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>45</td>
       <td>US48</td>
       <td>User Account Deactivation and Data Anonymization</td>
       <td>As a: HR / IT Administrator. I want to: Deactivate former employee accounts while retaining anonymized audit logs of their past system actions. So that: Historical compliance records remain intact without security risks.</td>
       <td>3</td>
    </tr>
    <tr>
       <td>46</td>
       <td>US47</td>
       <td>Customizable Dashboard Widget Layouts</td>
       <td>As a: Laboratory Operator. I want to: Drag, resize, and reorder dashboard widgets (heatmaps, line charts, alert feeds). So that: I can tailor my operational monitoring screen to focus on my primary tasks.</td>
       <td>5</td>
    </tr>
    <tr>
       <td>47</td>
       <td>US44</td>
       <td>In-App UI Theme and High-Contrast Accessibility Settings</td>
       <td>As a: Night-Shift Technician. I want to: Toggle between Light Mode, Dark Mode, and High-Contrast accessibility visual themes. So that: Display readability is optimized across varying laboratory lighting conditions.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>48</td>
       <td>US50</td>
       <td>Custom Email Signature and System Branding Settings</td>
       <td>As a: Lab Enterprise Admin. I want to: Upload corporate logos and customize email templates for system notifications. So that: System alerts and reports carry recognized company branding.</td>
       <td>2</td>
    </tr>
    <tr>
       <td>49</td>
       <td>US51</td>
       <td>Mobile Web Responsive Layout Optimization</td>
       <td>As a: On-Call Technician. I want to: Access the dashboard, acknowledge alerts, and record corrective actions from a smartphone browser. So that: I can respond to emergencies away from my desktop terminal.</td>
       <td>5</td>
    </tr>
	</tbody>
</table>

<img src="./assets/product-backlog.png" alt="Product Backlog" style="width: 100%; height: auto;">
