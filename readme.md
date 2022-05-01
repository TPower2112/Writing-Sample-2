# CrowdStrike: Falcon Sensor Upgrade for Big Sur
#### User Experience for the CrowdStrike Mac Sensor Upgrade Process


## Table Of Contents
1. [Why is this document important?](#docimport)
2. [What is the User Experience for endpoints not enrolled in JAMF](#uxnotjamf)

    A. [Approving Network Content Filtering](#netcon)
    
    B. [Approving System Extension](#sysext)
    
    C. [Approving Full Disk Access](#fda)
    
3. [The Apple "Falcon Notifications" Prompt](#appfalc)
4. [What happens if an end user chooses an incorrect prompt?](#incor)

### Why is this document important? <a name="docimport"></a>
After ugprading a Mac endpoint to Big Sur, CrowdStrike version 6.11 and above is required. M1 hardware support is scheduled for Q1 2021.  This document illustrates the correct security options the user mst choose to provide protection on the endpoint.

Please note if your workstation is managed by UBCIT or OKIT JAMF service, it will not receive the three prompts concerning enabling Network Filtering, the CrowdStrike Security Extension, and Full Disk Access.  These options are set automatically in the JAMF MDM profile.

If your Mac endpoint is not enrolled in JAMF, the end user must choose the correct option in order for CrowdStrike to function properly.

### What is the User Experience for endpoints not enrolled in JAMF <a name="uxnotjamf"></a>
The upgrade to the latest sensor occurs silently in the background with no restart or reboot required.  The end user will have to enable the following three prompts.
#### A. Approving Network Content Filtering <a name="netcon"></a>
The end user must allow the Falcon sensor to filter network content:


