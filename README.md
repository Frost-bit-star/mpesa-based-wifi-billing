# MikroTik MPesa WiFi Billing System

![GitHub License](https://img.shields.io/github/license/Frost-bit-star/mpesa-based-wifi-billing)
![GitHub Stars](https://img.shields.io/github/stars/Frost-bit-star/mpesa-based-wifi-billing)
![GitHub Issues](https://img.shields.io/github/issues/Frost-bit-star/mpesa-based-wifi-billing)
![GitHub Last Commit](https://img.shields.io/github/last-commit/Frost-bit-star/mpesa-based-wifi-billing)

![React](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react)
![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?logo=node.js)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql)
![MikroTik](https://img.shields.io/badge/Router-MikroTik-red)

A complete WiFi billing system that allows users to purchase internet access through **MPesa STK Push payments**.

Built for cybercafés, small businesses, WISPs, and public WiFi hotspots.

The system integrates with **MikroTik routers** to automatically manage user access after successful payments.

---

# Features

![MPesa](https://img.shields.io/badge/Payment-MPesa-green)
![Hotspot](https://img.shields.io/badge/Network-WiFi%20Hotspot-blue)

## MPesa STK Push

Users can pay for internet packages directly from their phones.

## Time-Based Access

Automatically control internet access based on purchased duration.

## Admin Dashboard

Manage:

- Users
- Payments
- Packages
- Router access

## MikroTik Integration

Automatically whitelist customer devices after payment confirmation.

---

# Remote MikroTik Management With TunGuard

![TunGuard](https://img.shields.io/badge/VPN-TunGuard-success)
![Self Hosted](https://img.shields.io/badge/Infrastructure-Self%20Hosted-blue)

Many MikroTik routers are behind CGNAT and do not have a public IP address.

**TunGuard** solves this by creating a secure private connection between your MikroTik network and a public server.

No public IP required.

## TunGuard Setup

1. Deploy TunGuard on a VPS with a public IP.
2. Connect your MikroTik router through the TunGuard tunnel.
3. Manage your hotspot remotely.
4. Allow your billing system to communicate with MikroTik securely.

TunGuard repository:

https://github.com/TunGuard/tanguard-binary

Useful for:

- WISPs behind CGNAT
- Remote hotspot management
- Distributed WiFi networks
- Secure MikroTik administration

---

# Architecture
Customer | | WiFi Hotspot | | MikroTik Router | | TunGuard Secure Tunnel | | Billing Server | | MPesa API

---

# Tech Stack

## Frontend

![React](https://img.shields.io/badge/React-Frontend-61DAFB?logo=react)
![Tailwind](https://img.shields.io/badge/TailwindCSS-UI-06B6D4?logo=tailwindcss)

- React
- Tailwind CSS


## Backend

![Node](https://img.shields.io/badge/Node.js-API-339933?logo=node.js)
![Express](https://img.shields.io/badge/Express-Framework-black?logo=express)

- Node.js
- Express


## Database

![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?logo=mysql)
![Prisma](https://img.shields.io/badge/Prisma-ORM-2D3748?logo=prisma)

- MySQL
- Prisma ORM


## Network

![MikroTik](https://img.shields.io/badge/MikroTik-Router-red)

- MikroTik RouterOS
- MAC Address Whitelisting

---

# Installation

## Clone Repository

```bash
git clone https://github.com/Frost-bit-star/mpesa-based-wifi-billing.git
```
#install Dependencies
```
npm install
```
Environment Variables
Create .env
```
MPESA_CONSUMER_KEY=your_key
MPESA_CONSUMER_SECRET=your_secret
MPESA_PASSKEY=your_passkey
MPESA_SHORTCODE=your_shortcode

DATABASE_URL=mysql://user:password@localhost/dbname

JWT_SECRET=your_secret

```
# Run Application
Backend
```
node index.js
```
Frontend
```
cd Frontend
npm install
npm run dev
```
## Security Improvements

- JWT authentication
- bcrypt password hashing
- protected admin routes
- Secure API handling
- mproved error handling
- MikroTik Workflow
- user connects to WiFi
```
        ↓

Selects internet package

        ↓

Pays via MPesa STK Push

        ↓

Payment callback received

        ↓

MAC address added to MikroTik

        ↓

Internet access enabled
```
### Contributing

Issues and pull requests are welcome.
License

MIT License
Contact

# Paid consultations and support:
hr@stackverify.site
