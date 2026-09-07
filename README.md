#  PawCare

### An Online Pet Adoption & Pet Care Services Platform

PawCare is a web-based platform designed to bring **pet adoption and pet-care services together in one trusted ecosystem**. It allows users to discover and adopt pets, list pets for adoption, find verified pet-care service providers, book appointments, and access helpful pet-care resources.

The platform uses a role-based and **admin-verified workflow** to improve trust, safety, and transparency throughout the pet adoption and care process.

---

##  Problem Statement

Pet adoption and pet-care services are often managed through scattered and informal channels such as social media, word-of-mouth, local contacts, and unregulated listings.

This creates several problems:

- Lack of authenticity and verification of pet listings
- Difficulty finding trustworthy pet-care providers
- Manual appointment coordination
- No centralized platform for adoption and pet services
- Limited guidance for first-time pet owners
- Lack of accountability for unreliable listings or service providers

PawCare aims to solve these problems by providing a **single, structured, and verified platform** for the complete pet ownership journey.

---

##  Our Solution

PawCare combines:

**Pet Discovery → Adoption → Pet Care → Service Booking → Pet Resources**

into a single platform.

Every pet listing, provider registration, and adoption request goes through an **admin verification workflow** before becoming publicly visible or actionable.

The platform also provides a **Pet Recommendation Quiz** that helps first-time owners identify suitable pet types based on their lifestyle, living environment, time availability, budget, and preferences.

---

#  Key Features

###  1. Pet Adoption
- Browse available pets
- Search and filter pets
- View detailed pet information
- Apply for adoption
- Track adoption requests
- List your own pet for adoption

###  2. Pet Search & Filters
Users can filter pets based on:
- Species
- Breed
- Age
- Gender
- Location
- Size

###  3. Adoption Request System
Users can submit adoption requests containing:
- Personal details
- Contact information
- Occupation
- Living environment
- Previous pet experience
- Reason for adoption

Requests are forwarded to the admin for verification and approval.

###  4. Pet Care Services
Users can discover and book services such as:
- Veterinary
- Grooming
- Training
- Walking
- Pet Sitting

###  5. Verified Service Providers
Service providers can register and create profiles containing:
- Qualification
- Experience
- Location
- Services
- Pricing
- Availability
- Reviews

Provider profiles become bookable after admin verification.

###  6. Service Booking
The booking workflow follows:

**Select Service → Select Date → Select Time → Enter Pet Details → Confirm Booking**

Booking statuses include:

`Pending → Confirmed → Completed / Cancelled`



### 7. Pet Care Resources
Educational guides cover:
- Dog Care
- Cat Care
- Before Adoption
- Pet Health
- New Pet Checklist

### 8. User Dashboard
Users can track:
- Adoption requests
- Service bookings
- Listed pets

###  9. NGO & Shelter Support
NGOs and shelters can register on the platform, submit verification documents, and list pets after approval.

###  10. Admin Verification
The administrator acts as the central verification layer for:
- Pet listings
- Service providers
- Adoption requests
- Bookings
- Users

---

# 👤 User Roles

##  Normal User / Pet Owner
A normal user can:
- Browse pets
- Apply for adoption
- List a pet for adoption
- Browse pet-care services
- Book appointments
- Access pet-care resources
- Track activities through their dashboard

##  Service Provider
Service providers can register as:
- Veterinarian
- Groomer
- Trainer
- Pet Walker
- NGO / Shelter
- Pet Business

After admin approval, providers can manage their profiles, services, bookings, and eligible pet listings.

##  Administrator
The administrator manages the entire platform.

Responsibilities include:
- Verify providers
- Verify pet listings
- Review adoption requests
- Manage bookings
- Manage users
- Deactivate suspicious accounts
- Maintain platform integrity

---

#  Module Description

@all 

Module Description

### 7.1 Authentication & Navigation

This module provides secure user registration and login, along with easy navigation through the main sections of the PawCare website.

### 7.2 Pet Adoption Module

This module allows users to browse available pets, view their details, and submit adoption requests. It also allows users to list pets for adoption, subject to admin approval.

### 7.3 NGO / Shelter / Pet Business Module

This module allows NGOs, shelters, and eligible pet businesses to register on the platform and list pets for adoption after verification and approval by the admin.

### 7.4 Pet Care Services Module

This module helps pet owners find and book services such as veterinary care, grooming, training, and pet walking. Service providers can manage their services and bookings through their dashboard.

### 7.5 Dashboard Module

This module provides separate dashboards for users and administrators. Users can track their adoption requests, pet listings, and service bookings, while administrators can manage users, pets, providers, requests, and bookings.

### 7.6 Resources – Pet Guide Module

This module provides useful pet-care information and guidance for pet owners. It includes a pet recommendation quiz that helps first-time users identify suitable types of pets based on their lifestyle and needs.

### 7.7 Database Layer

This layer stores and manages important information such as user accounts, pet details, adoption requests, service providers, services, and bookings, ensuring that the platform can access and manage information efficiently.

---

# System Workflow

```text
                    ┌──────────────────┐
                    │      PAWCARE     │
                    └────────┬─────────┘
                             │
              ┌──────────────┴──────────────┐
              │                             │
       ┌──────▼──────┐               ┌──────▼──────┐
       │ Pet Adoption │               │ Pet Services │
       └──────┬──────┘               └──────┬──────┘
              │                             │
       Browse Pets                    Browse Providers
              │                             │
       Select Pet                    Select Service
              │                             │
       Apply for Adoption             Book Appointment
              │                             │
              └──────────────┬──────────────┘
                             │
                      ┌──────▼──────┐
                      │    ADMIN    │
                      │ VERIFICATION│
                      └──────┬──────┘
                             │
                      Approval / Action
                             │
                      ┌──────▼──────┐
                      │    USER     │
                      │  DASHBOARD  │
                      └─────────────┘
```

---

#  Database Design

The system is built around six core entities.

### User
```text
id
name
email
password
role
```

### Pet
```text
id
name
type
breed
age
gender
location
image
description
owner/provider
status
```

Pet status:

```text
Pending
Approved
Adopted
Rejected
```

### AdoptionRequest
```text
user
pet
reason
status
```

### Provider
```text
user
type
business/organisation details
verification status
documents
```

### Service
```text
provider
category
price
description
availability
```

### Booking
```text
user
provider
service
pet
date/time
status
```

---

#  Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Backend | Node.js + Express.js |
| Database | MongoDB |
| Alternative Database | PostgreSQL |
| Authentication | Role-Based JWT / Session Authentication |
| Deployment | Render / Vercel |
| Development | Git & GitHub |

---

#  Authentication & Authorization

PawCare implements **Role-Based Access Control (RBAC)**.

```text
                    Login / Register
                          │
              ┌───────────┴───────────┐
              │                       │
          Pet Owner              Service Provider
              │                       │
       User Dashboard          Provider Dashboard
              │                       │
              └───────────┬───────────┘
                          │
                       Admin
                          │
                  Admin Dashboard
```

This ensures that users can only access functionality appropriate to their role.

---


# Team — BRIJCODERS

- **Samriddhi Bansal**
- **Gaurav Prajapati**
- **Kajal Saraswat**
- **Meenakshi**
- **Monika Chanchal**

---

#  Under the Guidance of

### Technical Trainer
**Akash Kumar Chaudhary**


