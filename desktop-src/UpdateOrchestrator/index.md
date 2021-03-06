---
title: Update Orchestrator API
description: UpdateOrchestrator schedules your automatic software updates with user impact in mind. 
ms.date: 01/13/2020
ms.topic: overview
---

# UpdateOrchestrator API

> [!IMPORTANT]
> The UpdateOrchestrator API is currently an “in development”  [limited access feature](/uwp/api/windows.applicationmodel.limitedaccessfeatures). This API will become publicly available in a future release.

**UpdateOrchestrator** schedules your automatic software updates with user impact in mind. This API allows you to schedule automatic download and installs, along with their requirements, in order to run updates at an optimal time that minimizes user-present impact. These features particularly benefit lower performance systems with limited or slower computing resources.

Windows 19H1 introduced a first-generation solution for automatic software update use cases that was adopted by OS updates and Store App updates and exposes an initial ‘Limited Access’ version of this API for a select set of  updaters of 'user-mode' apps as described below.

## Features

- Dynamically registers software updaters
 
- Invokes registered software updaters during optimal times, such as during user absence, to update 'user mode apps'.
    - Includes the ability to 'keep awake' on AC power to further reduce user-away impact.

- Operates on a Trust Model that only invokes trusted 3rd party registered software updaters
    - There are substantial risks when exposing UpdateOrchestrator to any and all callers such as updating BIOS firmware or drivers when a user is not present.  UpdateOrchestrator includes a trust model to mitigate these risks.



## Developer Audience

Use UpdateOrchestrator API if you already have background software updaters for Win32 'user mode' applications such as Adobe's updater for Acrobat Reader or Valve's Steam. This interface is not needed for UWP/Store applications as the Microsoft Store already takes advantage of this functionality for software updates.

To provide the best customer experience, this initial API release is scoped to a select set of registered updaters that meet the following criteria:


- Updates for 'user mode' applications only
- Do not involve BIOS/Firmware/Device or Software Drivers
    - Updating any BIOS, firmware, or device/software drivers, particularly those that have not passed a common quality criteria, pose a substantial risk when a user is not present. 
- Participating in the usage of this API entails being able to vouch for all content downloaded and installed by your background software updaters on users systems via audits. 

This API may be modified significantly before public release.   While UpdateOrchestrator API is under development, this initial release as a [limited access feature](/uwp/api/windows.applicationmodel.limitedaccessfeatures) is only for updaters that meet the above criteria at this time. 

Our aim is to improve the functionality of this API and reduce impact from multiple automatic software updaters on Windows. If you are interested in using this API, we would first appreciate your input through this [**brief survey**](https://aka.ms/UOAPISurvey) to help us understand how UpdateOrchestrator API can better serve your developer needs.

