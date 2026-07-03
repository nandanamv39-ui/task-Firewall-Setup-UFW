# task-Firewall-Setup-UFW
# Firewall Setup and Use (UFW)

## Objective

Configure and test firewall rules using UFW (Uncomplicated Firewall) on Linux.

---

## Tools Used

- Ubuntu Linux
- UFW (Uncomplicated Firewall)
- Terminal

---

## Steps Performed

### 1. Checked firewall status

```bash
sudo ufw status
```

Initially the firewall was inactive.

---

### 2. Enabled the firewall

```bash
sudo ufw enable
```

Verified the firewall became active.

---

### 3. Blocked Telnet (Port 23)

```bash
sudo ufw deny 23
```

Verified that the deny rule was added.

---

### 4. Tested the rule

Attempted a Telnet connection.

```
telnet localhost 23
```

The connection was refused, confirming that the firewall blocked access.

---

### 5. Allowed SSH (Port 22)

```bash
sudo ufw allow 22
```

This ensures SSH access remains available.

---

### 6. Removed the temporary Telnet block

```bash
sudo ufw delete deny 23
```

The final firewall configuration allows only SSH (Port 22).

---

## Final Firewall Rules

```
22 ALLOW Anywhere
22 (v6) ALLOW Anywhere (v6)
```

---

## Screenshots

- Firewall status before enabling
- Firewall enabled
- Port 23 blocked
- Telnet connection refused
- SSH rule added
- Final firewall rules

---

# Firewall Summary

A firewall filters incoming and outgoing network traffic based on predefined rules. It helps protect systems by blocking unauthorized access while allowing trusted connections.

---

# Interview Questions

## 1. What is a firewall?

A firewall is a security system that monitors and filters network traffic according to configured security rules.

---

## 2. Difference between Stateful and Stateless Firewall

Stateful Firewall:
- Tracks active connections
- Makes decisions based on connection state
- More secure

Stateless Firewall:
- Examines each packet independently
- Faster
- Does not remember previous packets

---

## 3. What are inbound and outbound rules?

Inbound rules control traffic entering the computer.

Outbound rules control traffic leaving the computer.

---

## 4. How does UFW simplify firewall management?

UFW provides an easy command-line interface for configuring Linux firewall rules without manually using iptables.

---

## 5. Why block Port 23 (Telnet)?

Telnet sends data, including passwords, in plain text, making it insecure. SSH (Port 22) is the secure replacement.

---

## 6. Common firewall mistakes

- Blocking SSH access accidentally
- Allowing unnecessary ports
- Forgetting to enable the firewall
- Using overly permissive rules

---

## 7. How does a firewall improve network security?

It blocks unauthorized access, reduces attack surface, filters malicious traffic, and protects network services.

---

## 8. What is NAT in firewalls?

Network Address Translation (NAT) allows multiple devices on a private network to share a single public IP address while hiding internal IP addresses.

---

## Outcome

Successfully configured UFW, tested firewall rules, blocked Telnet traffic, allowed SSH access, and restored the final firewall configuration.
