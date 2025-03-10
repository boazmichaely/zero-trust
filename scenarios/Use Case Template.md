# Use Case Template

This template provides a structured way to document use cases for the Zero Trust Validated Pattern. Each use case should clearly define the persona, goal, environment, workflows, security issues, and how Zero Trust addresses these issues.

---

## Persona
*Who is using the pattern?*

**Example**:  
*As a Security Architect, I need to secure a multi-tenant SaaS application running on OpenShift.*

---

## Goal
*What is the persona trying to accomplish?*

**Example**:  
*I want to ensure that communication between microservices is secure, even when some services are running on-premises and others in the cloud.*

---

## Why
*Why is this goal important? What are the risks or challenges?*

**Example**:  
*Without Zero Trust, lateral movement within the network could allow an attacker to compromise multiple services if one is breached.*

---

## Environment
*Describe the real-life environment the persona is working in.*

**Example**:  
*The environment includes an OpenShift cluster running on-premises, a public cloud provider (e.g., AWS), and legacy applications that cannot be containerized.*

---

## Workflows
*Detail the specific workflows or processes the persona follows.*

**Example**:  
*The DevOps engineer deploys microservices using Helm charts, configures CI/CD pipelines, and monitors the environment using Prometheus and Grafana.*

---

## Security Issues
*Identify the security gaps or risks in the current workflow.*

**Example**:  
*Currently, network policies are not enforced, and service-to-service communication relies on implicit trust within the cluster.*

---

## How Zero Trust Addresses the Issues
*Explain how the Zero Trust pattern mitigates the identified risks.*

**Example**:  
*By implementing Zero Trust, all service-to-service communication is authenticated and encrypted, and network policies enforce least-privilege access.*

## Type of customer or industry (optional)
*Identify the type of customer or industry where this use case is appliacble (Finance / Healthcare / Gov / Telco etc). Skip if this is applicable to everyone*

---

# Example Use Case: Multi-Tenant SaaS Application

## Persona
*As a Security Architect...*

## Goal
*I want to secure a multi-tenant SaaS application running on OpenShift.*

## Why
*Without Zero Trust, a compromised tenant could potentially access another tenant’s data, leading to a data breach and regulatory penalties.*

## Environment
*The application is hosted on an OpenShift cluster with multiple tenants. Each tenant has its own namespace, but some shared services (e.g., databases) are used across tenants.*

## Workflows
*Tenants onboard through a self-service portal, and their workloads are deployed in isolated namespaces. Shared services are accessed via APIs.*

## Security Issues
*Currently, there is no enforcement of tenant isolation at the network level, and shared services rely on IP-based access control.*

## How Zero Trust Addresses the Issues
*Zero Trust ensures that all communication between tenants and shared services is authenticated and authorized. Network policies enforce strict isolation, and mutual TLS (mTLS) encrypts all traffic.*

## Type of customer or industry
1. A Telco who manages a mult cluster environment for multiple vendors using ACM Hub
2. Large Enterprise managing infrastructure for internal tenants

---

# How to Use This Template
1. Copy this template for each new use case.
2. Replace the example content with details specific to the use case you're documenting.
3. Save the file with a descriptive name (e.g., `multi-tenant-saas.md`) in the `scenarios` folder.
4. Link the use case to relevant scenarios in the repository.

