# CrowdStrike: Falcon Sensor Upgrade for Big Sur
#### User Experience for the CrowdStrike Mac Sensor Upgrade Process


## Table Of Contents
1. [Why is this document important?](#docimport)
2. [The User Experience for endpoints not enrolled in JAMF](#uxnotjamf)

    A. [Approving Network Content Filtering](#netcon)

    B. [Approving System Extension](#sysext)

    C. [Approving Full Disk Access](#fda)

3. [The Apple "Falcon Notifications" Prompt](#appfalc)
4. [What happens if an end user chooses an incorrect prompt?](#incor)

### Objective <a name="docimport"></a>
Prior to upgrading a Mac endpoint to Big Sur, CrowdStrike version 6.11 and above is required. M1 hardware support is scheduled for Q1 2021.  This document illustrates the correct security options the user must choose to provide protection on the endpoint.

If your workstation is managed by UBCIT or OKIT JAMF service, the three options concerning enabling Network Filtering, the CrowdStrike Security Extension, and Full Disk Access are set automatically in the JAMF MDM profile.

### The User Experience for endpoints not enrolled in JAMF <a name="uxnotjamf"></a>
The upgrade to the latest sensor occurs silently in the background with no restart or reboot required.  The end user must enable the following three prompts.
#### A. Approving Network Content Filtering <a name="netcon"></a>
The end user must allow the Falcon sensor to filter network content. Please select **Allow** from the prompt below:

![Network Content Filter](https://github.com/TPower2112/Writing-Sample-2/blob/gh-pages/assets/images/Network-Content-Filter.png)

#### B. Approving System Extension <a name="sysext"></a>
Apple implemented [system extensions](https://support.apple.com/en-ca/guide/deployment/depa5fb8376f/web) instead of kernel extensions in Big Sur.  The end user will see the following prompt and must open Security Preferences.

![Security Preferences](https://github.com/TPower2112/Writing-Sample-2/blob/gh-pages/assets/images/System-Extension.png)

Under the General tab in Security & Privacy settings, select **Allow** for Falcon application.

![Allow System Extension](https://github.com/TPower2112/Writing-Sample-2/blob/gh-pages/assets/images/System-Extension-2.png)

#### C. Approving Full Disk Access <a name="fda"></a>
Full disk access is recommended for Mojave operating system and is required for Catalina and later. The end user must grant full disk access on the host. Administrator account permission is required.  Please follow the instructions below:

1. Select the Apple icon and Open System Perferences, then click Security & Privacy.
2. On the Privacy tab, if privacy settings are locked, select the lock icon and specify the          password.
3. In the left pane, select Full Disk Access.
4. In the right pane, select the plus icon and the check box next to Agent.
![Allow Full Disk](https://github.com/TPower2112/Writing-Sample-2/blob/gh-pages/assets/images/FDA-Agent.png)

### The Apple "Falcon Notifications" Prompt <a name="appfalc"></a>
The Falcon Notifications notifications prompt is displayed at the end of the installation.  Security Operations recommends the end user to select **Allow**.

![Allow Falcon Notifications](https://github.com/TPower2112/Writing-Sample-2/blob/gh-pages/assets/images/Notification-JAMF-CSInstall-Allow.jpg)

### What happens if an end user chooses an incorrect prompt <a name="incor"></a>
If an end user chooses an incorrect prompt, CrowdStrike will not operate properly. The end user can reload the system extensions by running the following command in the Terminal application:

    sudo /Applications/Falcon.app/Contents/Resources/falconctl load
