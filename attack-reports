# Brute Force Attack Detection

## Objective
Simulate a brute force login attack and detect it using SIEM monitoring and log analysis.

## Lab Environment

Attacker: Kali Linux  
Target: Ubuntu Server  
Monitoring: Wazuh SIEM  

## Attack Simulation

Command executed on attacker machine:

hydra -l admin -P passwords.txt ssh://192.168.1.15

The tool attempted multiple password combinations against the SSH service.

## Logs Observed

Example authentication log entries:

Failed password for admin from 192.168.1.10 port 49822 ssh2
Failed password for admin from 192.168.1.10 port 49823 ssh2

## Detection Method

Detection rule created to identify:

- Multiple failed login attempts
- Same source IP
- Short time window

SQL detection logic:

COUNT(failed_logins) > 5 within 1 minute

## Alert Trigger

SIEM generated alert:

"Multiple SSH authentication failures detected"

## Incident Analysis

Indicators:

Source IP: 192.168.1.10  
Target host: Ubuntu Server  
Attack type: Brute force authentication attack  

## Mitigation

- Block attacker IP via firewall
- Enable fail2ban
- Enforce strong password policy

## Lessons Learned

- Log correlation helps detect brute force attacks quickly
- Automated alerts reduce response time
