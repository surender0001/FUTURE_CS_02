
---

## UFW Configuration for Kali Linux

This document outlines the UFW (Uncomplicated Firewall) rules configured on your Kali Linux system.

### Firewall Rules Overview

Here are the UFW rules currently set up to manage network traffic:

| #  | Port/Service  | Action   | From               | To        | Protocol |
|----|---------------|----------|--------------------|-----------|----------|
| 1  | 22/tcp        | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 2  | 80/tcp        | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 3  | 22/tcp        | ALLOW IN | 192.168.83.128     | Anywhere  | TCP      |
| 4  | 443           | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 5  | 80            | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 6  | 3306          | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 7  | 22/tcp (v6)   | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 8  | 80/tcp (v6)   | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 9  | 443 (v6)      | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 10 | 80 (v6)       | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 11 | 3306 (v6)     | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |

### Detailed Explanation of Rules

1. **SSH Access (Port 22/tcp)**
   - **Rule Number:** 1
   - **Action:** ALLOW IN
   - **From:** Anywhere
   - **To:** Anywhere (TCP)
   - **Description:** Permits SSH connections from any IP address for remote management of the system.

2. **HTTP Access (Port 80/tcp)**
   - **Rule Number:** 2
   - **Action:** ALLOW IN
   - **From:** Anywhere
   - **To:** Anywhere (TCP)
   - **Description:** Allows unsecured web traffic over HTTP from any IP address.

3. **SSH Access (Port 22/tcp)**
   - **Rule Number:** 3
   - **Action:** ALLOW IN
   - **From:** 192.168.83.128
   - **To:** Anywhere (TCP)
   - **Description:** Permits SSH connections from the specific IP address 192.168.83.128.

4. **HTTPS Access (Port 443)**
   - **Rule Number:** 4
   - **Action:** ALLOW IN
   - **From:** Anywhere
   - **To:** Anywhere (TCP)
   - **Description:** Allows secure web traffic over HTTPS from any IP address.

5. **HTTP Access (Port 80)**
   - **Rule Number:** 5
   - **Action:** ALLOW IN
   - **From:** Anywhere
   - **To:** Anywhere (TCP)
   - **Description:** Allows unsecured web traffic over HTTP from any IP address.

6. **MySQL Access (Port 3306)**
   - **Rule Number:** 6
   - **Action:** ALLOW IN
   - **From:** Anywhere
   - **To:** Anywhere (TCP)
   - **Description:** Permits MySQL database connections from any IP address.

7. **SSH Access (Port 22/tcp) [IPv6]**
   - **Rule Number:** 7
   - **Action:** ALLOW IN
   - **From:** Anywhere (v6)
   - **To:** Anywhere (v6) (TCP)
   - **Description:** Permits SSH connections over IPv6 from any IP address.

8. **HTTP Access (Port 80/tcp) [IPv6]**
   - **Rule Number:** 8
   - **Action:** ALLOW IN
   - **From:** Anywhere (v6)
   - **To:** Anywhere (v6) (TCP)
   - **Description:** Allows unsecured web traffic over IPv6 from any IP address.

9. **HTTPS Access (Port 443) [IPv6]**
   - **Rule Number:** 9
   - **Action:** ALLOW IN
   - **From:** Anywhere (v6)
   - **To:** Anywhere (v6) (TCP)
   - **Description:** Allows secure web traffic over IPv6 from any IP address.

10. **HTTP Access (Port 80) [IPv6]**
    - **Rule Number:** 10
    - **Action:** ALLOW IN
    - **From:** Anywhere (v6)
    - **To:** Anywhere (v6) (TCP)
    - **Description:** Allows unsecured web traffic over IPv6 from any IP address.

11. **MySQL Access (Port 3306) [IPv6]**
    - **Rule Number:** 11
    - **Action:** ALLOW IN
    - **From:** Anywhere (v6)
    - **To:** Anywhere (v6) (TCP)
    - **Description:** Permits MySQL database connections over IPv6 from any IP address.

### Recent Changes

#### Rule Deletion

| #  | Port/Service  | Action   | From               | To        | Protocol |
|----|---------------|----------|--------------------|-----------|----------|
| 7  | 22/tcp (v6)   | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |

**Command Executed:**
```bash
$ sudo ufw delete 7
Deleting:
allow 22/tcp
Proceed with operation (y/n)? y
Rule deleted (v6)
```

#### Updated Firewall Rules

After deleting the rule for SSH over IPv6 (Port 22/tcp), the updated UFW rules are:

| #  | Port/Service  | Action   | From               | To        | Protocol |
|----|---------------|----------|--------------------|-----------|----------|
| 1  | 22/tcp        | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 2  | 80/tcp        | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 3  | 22/tcp        | ALLOW IN | 192.168.83.128     | Anywhere  | TCP      |
| 4  | 443           | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 5  | 80            | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 6  | 3306          | ALLOW IN | Anywhere           | Anywhere  | TCP      |
| 7  | 80/tcp (v6)   | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 8  | 443 (v6)      | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 9  | 80 (v6)       | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |
| 10 | 3306 (v6)     | ALLOW IN | Anywhere (v6)      | Anywhere  | TCP (IPv6) |

--------------
similarly other rules can also be deleted.

### How to Modify UFW Rules

To view the current UFW status and rules, run:

```bash
sudo ufw status verbose
```

For additional information, refer to the [Kali Linux Official Documentation](https://www.kali.org/docs/).


![Screenshot 2024-08-23 082740](https://github.com/user-attachments/assets/5eb40b9e-5dbb-4797-ac1f-98eab5cc5484)
![Screenshot 2024-08-23 082755](https://github.com/user-attachments/assets/4d5fd326-e29b-4cb7-8870-e1a2b2345d08)
![Screenshot 2024-08-23 083103](https://github.com/user-attachments/assets/e42c08d3-1e9a-4dd8-b379-4f7e1d49bfea)
![Screenshot 2024-08-23 083500](https://github.com/user-attachments/assets/7f227635-1f9e-4861-821c-bc5ff4583ab5)
![Screenshot 2024-08-23 084339](https://github.com/user-attachments/assets/512f655c-ebeb-4ea5-983e-ca77c231ef88)
![Screenshot 2024-08-23 084707](https://github.com/user-attachments/assets/fb6ee64e-65d5-4bdf-8ce4-15dd6800b661)
![Screenshot 2024-08-23 084731](https://github.com/user-attachments/assets/1c912df0-e981-4969-a2be-2a084253560b)
![Screenshot 2024-08-23 084928](https://github.com/user-attachments/assets/2f4e7fc2-e77d-4545-b2e0-5975ec10a9a4)
![Screenshot 2024-08-23 084951](https://github.com/user-attachments/assets/f1a6bff3-7416-4908-8a48-6f8a0f72808b)
![Screenshot 2024-08-23 085018](https://github.com/user-attachments/assets/b2a753b4-a7c1-4bce-983c-62c5b971ea8f)
![Screenshot 2024-08-23 085204](https://github.com/user-attachments/assets/2caee8bd-0ee5-4ace-b656-b3a1aa082c21)
