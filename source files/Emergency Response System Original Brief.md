# Project 1: Emergency Response System for Organisations

## Overview

Organisations need a reliable way to detect and respond to emergencies that may occur within their premises. Such emergencies could range from medical situations to security concerns. The system should be able to protect both regular employees and visitors, while being particularly mindful of situations where employees might be working alone.

## Core Requirements

### Emergency Detection Systems

- The organisation requires robust methods to detect emergency situations. This could involve both active reporting (where a person deliberately signals an emergency) and passive detection (where the system automatically detects potentially dangerous situations like falls). The solution should consider the variety of ways emergencies can be reported while ensuring the system is not prone to false alarms.
- Special attention should be given to different types of emergencies that might require different response protocols. For instance, a medical emergency for an individual might need a different response compared to a facility-wide emergency.

### Communication Framework

- The system needs a reliable way to receive emergency signals from various points within the premises and channel them to a central processing point. This communication should be fail-safe and have redundancy built in to ensure no emergency signal is lost.
- The central processing system must be capable of interpreting the type and location of the emergency and initiating appropriate response protocols. This includes determining who needs to be notified based on the nature and severity of the emergency.

### User Management System

- The solution must maintain accurate information about regular employees including their contact details and any special medical or emergency considerations.
- A system is needed to temporarily register visitors and maintain their emergency contact information while they are on the premises. This system should automatically remove visitor data when it's no longer needed. It can be assumed that a visitor sign-in system is operational.
- Privacy considerations must be built into the data management system, ensuring that personal information is protected while still being instantly accessible during emergencies.