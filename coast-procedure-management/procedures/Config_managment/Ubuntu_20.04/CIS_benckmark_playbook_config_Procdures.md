Coast Autonomous Secure Configuration Management Procedure guide:

Ubuntu 20.04

1. Purpose

- The purpose of this procedure guide is to address the need to harden the embedded ubuntu-based systems, responsible for the sensor functions and locations services within Coast ARM platform. The need for this hardening is address via:
  - Configuration management policy/baseline policies
  - Nist 800-53 compliance
  - Compliment security tools/services
  - Client expectations
  - Coast’s security plan objectives

1. Guide
2. Confirm that the pc has been flashed
    1. <https://github.com/coast-autonomous/install-script>
3. Clone the playbook repo and run the play script with the right config files. Steps and files can be found at this link:
    1. <https://coast-autonomous-robotics.atlassian.net/wiki/spaces/CCSDR/pages/1223491585/Ubuntu+20.04+aka+UBUNTU20-CIS>
4. Run the configurations for the true positives, and “extra false positives”, configurations are found here:
    1. <https://github.com/george-coast/coast-policy-management/blob/main/coast-policy-management/policies/CIS_Ubuntu_20.04_Assessment.md>
5. Turn on the UFW and run the flowing commands to prevent ssh lock out and wazuh functions:

| sudo ufw allow out proto tcp to 192.168.1.100 port 1514 |
| --- |
| sudo ufw allow out proto udp to 192.168.1.100 port 1514 |
| sudo ufw allow out proto tcp to 192.168.1.100 port 1515 |
| sudo ufw allow OpenSSH |
| sudo ufw allow 22 |
