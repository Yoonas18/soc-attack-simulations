# Port Scan Detection

## Objective
Detect network scanning activity using log monitoring.

## Attack Tool
Nmap

Command used:

nmap -sS 192.168.1.20

## Detection

Network logs showed:

Multiple connection attempts across ports 22, 80, 443, 8080.

## Indicators

High number of connection attempts in short time window.

## Mitigation

- Block scanning IP
- Implement IDS alerts
- Monitor abnormal traffic spikes
