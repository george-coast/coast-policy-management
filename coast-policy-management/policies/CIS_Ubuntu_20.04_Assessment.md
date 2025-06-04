Coast’s Security CIS benchmark assessment

Purpose

The purpose of this document is to provide an assessment, that looks to view the state of the system after the recommend: https://ncp.nist.gov/checklist/revision/5771 CIS configuration has been applied. As well as provide a procedure guide on how to achieve the CIS configuration score.

Scoring Guide

The assessment will result in two types of scores: initial scores via the Wazuh’s Security configuration assessment and a score that combines the Wazuh’s Security configuration assessment and false positives.

Note the scoring guide before the false positives is dictated after running the ansible playbooks, procedure and guide can be found here: https://coast-autonomous-robotics.atlassian.net/wiki/spaces/CCSDR/folder/1200160785

Score before false positives:



| Passed | Failed | Not Applicable | Score |
| --- | --- | --- | --- |
| 112 | 67 | 3 | 62% |

Score after the false positives:



| Passed | Failed | Not Applicable | Score |
| --- | --- | --- | --- |
| 141 | 38 | 3 | 77% |

False positives:



| ID | Description | Commands | Reason for FP |
| --- | --- | --- | --- |
| 28531 | Ensure Automatic Error Reporting is not enabled. | systemctl --now disable apport.service | The service was already disabled. |
| 28532 | Ensure core dumps are restricted. | sysctl -w fs.suid_dumpable=0 | Fs.suid_dumpable is already set to 0. Regardless system-coredump is not even installed. |
| 28537 | Ensure message of the day is configured properly. | Nano /etc/motd | Already configure with a message, applied extra configs to display on ssh |
| 28549 | Ensure ntp is running as user ntp. | apt purge ntp | Ntp was never installed, plus chrony is running. |
| 28550 | Ensure ntp is enabled and running. |  | ID: 28549 |
| 28566 | Ensure rsync service is either not installed or masked. | apt purge rsync | Rsync is already masked and inactive. |
| 28614 | Ensure systemd-journal-remote is installed. | apt install systemd-journal-remote | No need to install this, Wazuh conducts the same function. |
| 28622 | Ensure journald is configured to send logs to rsyslog. | Edit the /etc/systemd/journald.conf file and add the following line: ForwardToSyslog=yes Restart the service: # systemctl restart rsyslog. | Line was already in the config. |
| 28623 | Ensure rsyslog default file permissions are configured. | Edit either /etc/rsyslog.conf or a dedicated .conf file in /etc/rsyslog.d/ and set $FileCreateMode to 0640 or more restrictive: $FileCreateMode 0640 Restart the service: # systemctl restart rsyslog | Config was already applied. |
| 28665 | Ensure minimum days between password changes is configured. | Set the PASS_MIN_DAYS parameter to 1 in /etc/login.defs : PASS_MIN_DAYS 1 | Already set to 1 |

Extra Configs of false positives



| ID | Configs |
| --- | --- |
| 28540 | Nano /etc/ssh/sshd_configAdd the flowing line: PrintMotd yesRestart: sudo systemctl restart sshd |
|  |  |
|  |  |

Extra Configs of true positives:



| ID | Configs |
| --- | --- |
| 28543 | Apt purge gdm3 |
| 28546 | systemctl unmask chronysystemctl enable chronysystemctl start chrony |
| 28551 | apt purge xserver-xorg* |
| 28552 | apt purge avahi-daemon |
| 28554 | apt purge isc-dhcp-server |
| 28572 | apt purge rpcbind |
| 28575 | Review the procedure guide at the bottom. |
| 28576 | Already enabled once the right after the UFW comes on, but the command ufw deny in from ::1 needs to be ran |
| 28577 | ufw default deny incomingufw default deny outgoingufw default deny routed |
| 28611 | Sudo chown root /sbin |
| 28617 | Nano /etc/systemd/journald.confUncomment: Compress=yes |
| 28618 | Nano /etc/systemd/journald.confUncomment: Storage= auto                       and change to                                                                                     Storage=persistent |
| 28632 | sudo chown root:root /etc/cron.allowsudo chmod 640 /etc/cron.allowsudo nano /etc/cron.allowAdd user: mic-733ao |
| 28633 | chmod g-wx /etc/at.allowo-rwx /etc/at.allowchown root:root /etc/at.allow |
| 28653 | Nano /etc/ssh/sshd_config Add:     ClientAliveInterval 15   ClientAliveCountMax 3 |
| 28662 | sudo cp /etc/pam.d/common-auth /etc/pam.d/common-auth.baksudo cp /etc/security/faillock.conf /etc/security/faillock.conf.baksudo nano /etc/pam.d/common-authadd:# here are the per-package modules (the "Primary" block)auth required pam_faillock.so preauth          # Added to enable faillockauth [success=1 default=ignore] pam_unix.so nullokauth [default=die] pam_faillock.so authfail    # Added to enable faillockauth sufficient pam_faillock.so authsucc       # Added to enable faillocksudo nano /etc/pam.d/common-accountEnsure the following line is added at the end:account required pam_faillock.sosudo nano /etc/security/faillock.confadd/uncomment:deny = 4fail_interval = 900unlock_time = 600 |
| 28663 | nano /etc/pam.d/common-passwordchange: password [success=2 default=ignore] pam_unix.so obscure use_authtok try_first_pass yescryptto: password [success=1 default=ignore] pam_unix.so obscure use_authtok try_first_pass yescrypt remember=5 |
| 28664 | nano /etc/login.defschange: ENCRYPT_METHOD to   ENCRYPT_METHOD yescryptx |
| 28668 | useradd -D -f 30 |

Assessment Evaluation

After conducting the cis benchmark playbook and the configurations listed as “true positives”, we can conclude that system is better harden and is accordance with the NIST 800-53 specifically the following controls:

AC-2: Account Management

AC-6: Least Privilege

AU-2: Audit Events

AU-6: Audit Review

CM-2: Baseline Configuration

CM-6: Configuration Settings

CM-7: Least Functionality

IA-2: Identification and Authentication (Organizational Users)

IA-5: Authenticator Management

SC-7: Boundary Protection

SC-12: Cryptographic Key Establishment

SC-28: Protection of Information at Rest

SI-2: Flaw Remediation

SI-3: Malicious Code Protection

SI-4: Information System Monitoring

Note: This is NOT the only security that should be applied to the embedded system, other configurations and tools are to be applied to achieve the full objective for Nist 800-53. This should be viewed as a defense layer that helps in the over all security, and that there are redundant tools that should be applied to for example siem and ids.