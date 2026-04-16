 # 📘 Day 4 – Cisco IOS CLI (Short Notes + Interview Q&A)

 

## 🔹 Connecting to Cisco Device

* Use console port (RJ45 / USB)
* Rollover cable used for RJ45 console
* Terminal software: PuTTY

---

## 🔹 Cisco IOS Modes

### 1. User EXEC Mode

* Prompt: Router>
* Limited access
* Cannot make configuration changes

### 2. Privileged EXEC Mode

* Command: enable
* Prompt: Router#
* Full view access, can save/restart
* Cannot directly configure

### 3. Global Configuration Mode

* Command: configure terminal / conf t
* Prompt: Router(config)#
* Used to configure device

---

## 🔹 CLI Shortcuts

* ? → show commands
* Tab → auto-complete
* Partial commands allowed
* Ambiguous command → error

---

## 🔹 Password Configuration

### Enable Password

enable password CCNA

* Plain text (not secure)

### Enable Secret

enable secret password

* Encrypted (MD5)
* More secure

### Service Password Encryption

service password-encryption

* Encrypts passwords (weak encryption)
* Does not affect enable secret

---

## 🔹 Configuration Files

* Running-config → active config (RAM)
* Startup-config → saved config (NVRAM)

---

## 🔹 Commands

show running-config
show startup-config

write
write memory
copy running-config startup-config

---

## 🔹 Important Points

* Passwords are case-sensitive
* enable secret overrides enable password
* no command removes configuration

---

# ❓ Interview Questions with Answers

## 🔸 Basic

Q1. What is CLI?
A. CLI (Command Line Interface) is a text-based interface used to configure and manage Cisco devices using commands.

Q2. Difference between GUI and CLI?
A. GUI uses graphical elements (buttons, windows), while CLI uses text commands. CLI is faster, more powerful, and preferred in networking.

Q3. What is User EXEC mode?
A. It is the initial mode (Router>) with limited access where users can only view basic information and cannot make changes.

---

## 🔸 Intermediate

Q4. Difference between enable password and enable secret?
A. Enable password is stored in plain text (less secure), while enable secret is encrypted (MD5) and more secure. If both are configured, enable secret is used.

Q5. Difference between running-config and startup-config?
A. Running-config is the current active configuration in RAM, while startup-config is saved in NVRAM and loaded after reboot.

Q6. How do you save configuration in Cisco device?
A. Using commands:

* write
* write memory
* copy running-config startup-config

---

## 🔸 Scenario-Based

Q7. You configured a router but lost config after reboot. Why?
A. Because the configuration was not saved to startup-config. Only running-config was modified.

Q8. You can’t enter privileged mode even with correct password. Why?
A. Possible reasons:

* Password is case-sensitive (Caps Lock issue)
* Wrong password entered
* enable secret is configured and overriding enable password

---

## 🔁 Quick Revision

* CLI is used to configure devices
* Modes: User > Privileged > Global Config
* Running-config = current, Startup-config = saved
* enable secret is most secure

---
