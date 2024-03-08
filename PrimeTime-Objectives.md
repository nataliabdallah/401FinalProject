## BTO1: Initial Threat Model and STRIDE Analysis

**Identify the System Components: Map out the components of your project, including assets, data flows, and processes. For a web application like SimCorp's, this includes the web server, application code, databases, and any external integrations.**

**Construct a Data Flow Diagram (DFD): Create a DFD to visualize how data moves through your system. Include external entities, processes, data stores, and data flows.**

*Perform STRIDE Analysis:*
- Spoofing: Identify where authentication is used and assess its strength.
Tampering: Look for places where data is stored or transmitted and evaluate the integrity controls.
- Repudiation: Check for logging mechanisms and whether they're sufficient to prove actions.
- Information Disclosure: Assess confidentiality controls over sensitive data.
- Denial of Service: Evaluate the system's resilience against service disruptions.
- Elevation of Privilege: Identify where permissions are checked and if they can be bypassed.

## BTO2: Deploy Threat Detection Tooling

**Evaluate and Select Tools: Research tools that can provide visibility into your environment, such as SIEM (Security Information and Event Management), IDS/IPS (Intrusion Detection and Prevention Systems), and endpoint detection and response solutions.**

**Deploy and Configure: Install these tools following vendor instructions. Ensure coverage across your environment for comprehensive monitoring.**

## BTO3: Configure Detection Methods
*For IDS Rules:*

- Identify common attack patterns against web applications, such as SQL injection or cross-site scripting (XSS).
- Write or customize IDS rules to alert on signatures or behaviors indicative of these attacks.
- Test the rules to ensure they trigger on malicious activity but minimize false positives.

*For Web Server Detective Controls:*

- Enable detailed logging on the web server and the application itself. Ensure logs capture access requests, user actions, and system errors.
- Implement file integrity monitoring on the web server to detect unauthorized changes.

## BTO3a: Implement Detective Controls for Key Assets

*Web Application Firewalls (WAF): Deploy a WAF in front of the web server to inspect incoming HTTP/HTTPS requests and block malicious ones.*

*Access Control Lists (ACLs): Configure ACLs to restrict access to the web server from unauthorized IP addresses.*

*Regular Vulnerability Scanning: Schedule scans to identify and remediate vulnerabilities in the web application.*

## BTO4: Observe Adversarial Actions
*Monitor Logs and Alerts: Regularly review logs from your IDS, WAF, and other monitoring tools for suspicious activity.*

*Document Evidence: Keep detailed records of any identified scanning activities, attempted exploits, and other TTPs used by attackers.*

*Collect IOCs: Gather indicators of compromise, such as malicious IP addresses, URLs, file hashes, and suspicious payloads.*
## BTO5: Implement Scripted Automation for Alerts
*Develop Scripted Automation:*

- Write scripts that can analyze logs and alerts from your detection tools to identify patterns indicative of adversarial activity.
- Use scripting languages like Python or PowerShell, depending on your environment and the capabilities of your monitoring tools.
- Test and Refine: Simulate attack scenarios to ensure your automation scripts accurately identify and alert on malicious activity.
- Operationalize: Integrate your scripts into your regular monitoring and incident response processes. Ensure they run at regular intervals or trigger based on specific events.
- Alerting Mechanism: Configure your scripts to send alerts through email, SMS, or a centralized incident response platform when they detect potential adversarial activity.

Written by: - [Brittany Powell](https://github.com/Bmjohnson87)