# risk monitoring with wazuh lab report

## executive summary

this lab focused on implementing a practical detective control to monitor and report unauthorized file activity from a risk management perspective.

the objective was to detect file creation, modification, and deletion on a monitored endpoint using wazuh file integrity monitoring (fim).

wazuh was deployed as a centralized monitoring platform, and fim was configured on a sensitive folder within a windows endpoint.

this implementation demonstrates how technical controls support governance, risk, and compliance (grc) by improving visibility, generating audit evidence, and strengthening continuous monitoring.

---

## key findings

- wazuh was successfully deployed as a centralized monitoring platform  
- windows endpoint was successfully enrolled as an active agent  
- file integrity monitoring was configured on a sensitive folder  
- file creation, modification, and deletion events were successfully detected  
- wazuh generated centralized alerts with timestamps, file paths, and checksums  

---

## recommendations

- restrict write access to sensitive folders using role-based access control  
- implement preventive controls alongside detective monitoring  
- review file activity trends regularly for abnormal behavior  
- retain centralized monitoring logs for audit and compliance purposes  

---

## methodology

### environment setup
- server os: ubuntu / kali linux  
- endpoint os: windows host machine  
- monitoring platform: wazuh  
- network configuration: bridged adapter  

### tools used
- wazuh manager  
- wazuh dashboard  
- wazuh agent  
- windows services  
- browser (firefox)  

---

## task 1: wazuh manager deployment

### commands used
curl -s https://packages.wazuh.com/key/gpg-key-wazuh | sudo gpg --dearmor -o /usr/share/keyrings/wazuh-archive-keyring.gpg

curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a -i  

### approach
wazuh was installed as the centralized monitoring platform including manager, indexer, and dashboard components.

### results
- wazuh successfully deployed  
- services initialized  
- dashboard accessible via server ip  
- environment ready for agent enrollment  

---

## task 2: agent installation and registration

### command used
sudo /var/ossec/bin/manage_agents  

### approach
the wazuh agent was installed on the windows host machine and registered with the wazuh manager using a generated key.

### results
- agent successfully installed  
- endpoint successfully registered  
- system visible in wazuh dashboard  
- secure communication established  

---

## task 3: file integrity monitoring implementation

### configuration
<directories realtime="yes">c:\users\francisca\sensitivefiles</directories>

### approach
file integrity monitoring was configured to track file changes in real time inside a sensitive directory.

### results
- real-time monitoring enabled  
- syscheck active  
- file creation, modification, and deletion detected  

---

## task 4: risk monitoring and validation

### approach
a test file named q4_financial_forecast.docx was created, modified, and deleted inside the monitored folder to simulate unauthorized activity.

### results
- file creation detected  
- file modification detected  
- file deletion detected  
- alerts logged in wazuh dashboard  
- events included timestamps, file paths, and action types  

---

## grc analysis

### risk identification
unauthorized changes to financial documents may result in:
- financial misstatements  
- operational disruption  
- reputational damage  

### control evaluation
- detective control: wazuh fim detects file changes after they occur  
- preventive control: role-based access control recommended  
- corrective control: restore from backups and investigate user activity  

### monitoring and reporting
key metrics:
- total file integrity alerts  
- frequency of file modifications  
- response time to alerts  

centralized logging improves audit readiness and governance visibility.

---

## compliance mapping

wazuh supports compliance by providing:
- timestamped logs  
- file integrity tracking  
- centralized audit evidence  

auditors can validate file activity by filtering logs based on file path and time period.

---

## conclusion

this lab demonstrates how wazuh transforms file monitoring into a structured governance, risk, and compliance control system.

it improves visibility, strengthens audit readiness, and supports continuous monitoring of sensitive data.
