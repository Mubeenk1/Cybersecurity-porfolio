# ☁️ AZ-900 Mini Project – Creating a Virtual Machine in Azure

## 📘 Overview

This mini lab is part of my ongoing AZ-900 learning journey. In this activity, I deployed a **Windows Server 2019 virtual machine** in the Microsoft Azure cloud platform. This exercise helped me understand the core components involved in creating and managing cloud-based infrastructure. Dive into the PDF to examine the screenshot and steps I took to create a VM

---

## 🎯 Objective

- Create and configure a basic virtual machine in Azure.
- Understand VM provisioning steps such as region selection, image type, authentication, and inbound port rules.
- Test connectivity by installing IIS and accessing the default web page through a browser.

---

## 💡 Azure Concepts Covered

### 🔹 Virtual Machines (VMs)
Azure Virtual Machines provide **Infrastructure as a Service (IaaS)**. This allows full control over the operating system, the ability to run custom software, and flexibility in configuring hosting environments. VMs provide the benefits of virtualization without the need to purchase or maintain the underlying hardware.  
As part of the IaaS model, we are responsible for configuring, updating, and maintaining the software that runs on the VM.

### 🔹 VM Images
A **VM image** is a template used to create a virtual machine. It includes an operating system and can optionally include preconfigured apps.  
In this lab, I selected the image:  
**Windows Server 2019 Datacenter – Gen2**

### 🔹 Resource Groups
A **resource group** in Azure is a logical container that holds related resources for an Azure solution. All the resources for this lab (VM, networking, storage) were grouped under:  
**Resource Group Name**: `MyVmRG`

### 🔹 Azure Regions
An **Azure Region** is a geographical area that contains multiple datacenters connected through a low-latency network. Azure allocates and manages resources within regions to balance workloads and optimize performance.  
For this lab, I selected the region:  
**Australia East** — located in New South Wales (Sydney), closest to my location.

---

## 🔧 Lab Steps

1. Navigated to Azure Virtual Machines section.
2. Created a new VM with the above configurations.
3. Connected to the VM using RDP.
4. Installed IIS via PowerShell:

   ```powershell
   Install-WindowsFeature -Name Web-Server -IncludeManagementTools

