# AWS-Factory-Testing-System-Architecture

Architecture design of a cloud-based factory testing form system built on AWS serverless services.  Factory operators use tablet devices to record tool performance and calibration test data to the cloud, enabling centralized management for operational monitoring and downstream tool data analysis.

## Background

In factory environments, testing and calibration processes often rely on paper-based records or fragmented digital tools, which can lead to
inconsistent data management and limited visibility for supervisors.

A cloud-based system enables centralized data collection, real-time access, and improved traceability while reducing operational overhead on-site.

## Architecture Overview

The system is designed using AWS serverless services to minimize infrastructure maintenance while providing scalability and reliability.

Factory operators access a tablet-friendly web interface hosted on Amazon S3.

All requests are routed through Amazon API Gateway to AWS Lambda functions, which handle authentication, business logic, and database interactions.
Persistent data is stored in Amazon RDS.

## Core System Components

- Frontend (S3 + Browser):
  A lightweight, tablet-friendly web interface for form-based data entry.

- API Gateway:
  Serves as the unified entry point for all client requests and enforces request validation.

- AWS Lambda:
  Implements authentication, role-based access control, and application logic.

- Database (RDS):
  Stores testing records with relational structure and audit-related fields.

## Data Design Principles

The data layer is designed with an emphasis on standardization and extensibility.

Core principles include:

1.A set of shared, standardized fields applied across records

2.Consistent naming and data types to support long-term maintainability

3.Schema designs that allow new data attributes to be introduced without impacting existing standardized structures

4.Data organization that facilitates downstream reporting and analytical use cases


## Security Considerations

Security is enforced at multiple layers of the system:

- JWT-based authentication for API access
- Role-based authorization to restrict system functions
- No direct database access from the client
- All sensitive operations handled within AWS-managed services

## Scope and Disclaimer

This repository focuses on architectural design and system concepts only.

All workflows, schemas, and examples are simplified and fictional. This project
does not include production business logic or proprietary implementations and is intended solely for demonstration purposes.

## Architecture Overview


<img width="1396" height="527" alt="image" src="https://github.com/user-attachments/assets/4e7aee82-5ae9-426a-8064-6b5cc6c52544" />





## User Interface (Example)

The user interface is organized around a centralized menu that provides access to four core functions of the system.


- Test forms allow authorized users to submit testing or calibration data, which is processed and stored by backend services. 


- Submitted records can be reviewed and managed through the query interface, where users retrieve data based on filters and permissions.


- Aggregated dashboards present summarized metrics and trends derived from stored records, supporting monitoring and oversight.

- Account management functions enable administrators to manage user access and role permissions across the
system.

All interface actions follow the same backend architecture and are governed by authentication and role-based access control.

(Detailed test form pages are not shown in this repository.
While form-based data entry is fully implemented in the system, these screens
are closely tied to domain-specific workflows. This repository therefore
focuses on architecture and system capabilities for public demonstration.)


**| Main Menu |**
<img width="1396" height="527" alt="image" src="https://github.com/Naenaedadader/AWS-Factory-Testing-System-Architecture/blob/main/menu_demo.png" />

**| Query  |**
<img width="1396" height="527" alt="image" src="https://github.com/Naenaedadader/AWS-Factory-Testing-System-Architecture/blob/main/Search_demo.png" />

**| Account Management |**
<img width="1396" height="527" alt="image" src="https://github.com/Naenaedadader/AWS-Factory-Testing-System-Architecture/blob/main/account_manage_demo.png" />

**| Dashboard (Example Data) |**
<img width="1396" height="527" alt="image" src="https://github.com/Naenaedadader/AWS-Factory-Testing-System-Architecture/blob/main/dashboard_demo%E5%9C%96.png" />

