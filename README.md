# 📌 Subnetting Made Easy!

## 🚀 Introduction
Subnetting is an important concept in networking, but it can be complex and confusing. Many people struggle with it, and traditional learning methods often make it harder to understand.

However, I discovered a **fast and easy** method that simplifies subnetting, and I wanted to share it with you! This guide will help you learn subnetting quickly, without unnecessary complexity.

---

## 📖 Understanding Subnetting Basics
When you type `ipconfig` in **CMD (Command Prompt)**, you see your **IPv4 address** and **Subnet Mask** (e.g., `255.255.255.0`). But what do these numbers mean?

- These values are represented in **binary (1s and 0s)**.
- IPv4 addresses are divided into **8-bit segments** (e.g., `8.8.8.8`).
- If all **8 bits are ON (1s)**, the result is `255`. If all **bits are OFF (0s)**, the result is `0`.

### 🎯 Example:
```
255.255.255.0 → 11111111.11111111.11111111.00000000
```
Each **ON bit** contributes to the subnet mask, and the remaining bits define available hosts.

---

## 🔢 Quick Subnet Calculation
### 📌 Understanding the "Bits Table"
The **bits table** helps us determine subnet masks quickly:

| Bit Position | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 |
|-------------|---|---|---|---|---|---|---|---|
| Value       | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

### 📌 Subnet Masks Based on CIDR Notation
| CIDR | Subnet Mask | Total Hosts |
|------|------------|-------------|
| /8   | 255.0.0.0  | 16,777,214  |
| /16  | 255.255.0.0 | 65,534      |
| /24  | 255.255.255.0 | 254 |
| /25  | 255.255.255.128 | 126 |
| /26  | 255.255.255.192 | 62 |
| /27  | 255.255.255.224 | 30 |
| /28  | 255.255.255.240 | 14 |
| /29  | 255.255.255.248 | 6  |
| /30  | 255.255.255.252 | 2  |
| /32  | 255.255.255.255 | 1 (single host) |

🔹 **Rule**: The more bits turned ON (1s), the **fewer hosts** available.

---

## 🔥 Why is /24 Common?
A **/24 network** (`255.255.255.0`) allows **256 IPs** and is commonly used for:
- Home networks 🏠
- Small businesses 🏢

For **larger networks**, we need a **/16** or **/8** subnet, which supports more hosts.

---

## 🔥 Fast Subnetting Method
1. **Use the bits table**: Start from `128` and go down (`128, 64, 32, 16, 8, 4, 2, 1`).
2. **Identify how many bits are ON**.
3. **Match it to the corresponding subnet mask** (use the cheat sheet above).
4. **Calculate available hosts**: \(2^n - 2\) (subtracting network & broadcast addresses).

---

## 🛠️ Example Subnet Calculations
### 🎯 **Subnet: 192.168.1.0/24**
- Subnet Mask: `255.255.255.0`
- Available Hosts: `256 - 2 = 254`
- Network ID: `192.168.1.0`
- Broadcast Address: `192.168.1.255`

### 🎯 **Subnet: 192.168.1.0/26**
- Subnet Mask: `255.255.255.192`
- Available Hosts: `64 - 2 = 62`
- Network ID: `192.168.1.0`
- Broadcast Address: `192.168.1.63`

### 🎯 **Subnet: 192.168.1.0/27**
- Subnet Mask: `255.255.255.224`
- Available Hosts: `32 - 2 = 30`
- Network ID: `192.168.1.0`
- Broadcast Address: `192.168.1.31`

🔹 **Rule of Thumb**: Every time a bit is turned OFF, the number of hosts **doubles**.

---

## 🎥 Learn More!
If you're still confused, don’t worry! Watch **Professor Messer’s "Seven Second Subnetting"** video for an even easier method:

📌 **[Watch Here](https://www.youtube.com/watch?v=ZxAwQB8TZsM)**

✅ **Keep practicing, and subnetting will become second nature!** 🚀

🛠️ Online Subnet Calculator
Here is a simple online subnet calculator made by David C:  **[Subnet Calculator](https://www.davidc.net/sites/default/subnets/subnets.html)**

