# ExternalAIHardeningBaseline
External AI hardening baseline for Windows 11

# Prerequisites

Before importing the policies in this repository https://github.com/vladjoh/ExternalAIHardeningBaseline/tree/main/ExternalAiHardeningW11, ensure your Microsoft 365 environment meets the following requirements and some settings needs to be turned on manually.

## Requirements

- ✅ **Microsoft Defender for Endpoint**
  - Microsoft Defender for Endpoint must be activated and configured in your tenant.

- ✅ **Microsoft 365 Licensing**
  - Users must be assigned one of the following licenses:
    - Microsoft 365 Business Premium with Defender Suite
    - Microsoft 365 E3
    - Microsoft 365 E5
    - Microsoft 365 E7

- ✅ **Microsoft Intune**
  - Microsoft Intune must be configured as the Mobile Device Management (MDM) authority.

  intune.microsoft.com->Devices-> Enrollment -> Automatic Enrollment

  <img width="1115" height="807" alt="image" src="https://github.com/user-attachments/assets/ae1527dd-0e7f-46c0-b63e-18d8f24ec2db" />


- ✅ **Microsoft Defender for Endpoint Integration**
  - In the Microsoft Defender portal, navigate to:
    ```
    Settings → Endpoints
    ```
  - Enable the **Microsoft Intune connection**.
<img width="1451" height="609" alt="image" src="https://github.com/user-attachments/assets/fed83e08-2029-4e95-9775-16d872e20bdc" />

  

- ✅ **Microsoft Defender for Cloud Apps Integration**
  - In the Microsoft Defender portal, navigate to:
    ```
    Settings → Endpoints 
    ```
  - Microsoft Defender for Cloud Apps (MDCA)

  <img width="1467" height="1081" alt="image" src="https://github.com/user-attachments/assets/018f04ec-5ab3-4577-9f39-41f53b1fca68" />


- ✅ **Endpoint Features**
  - In the Microsoft Defender portal, navigate to:
    ```
    Settings → Endpoints

  - Ensure the following features are enabled:
    - Custom Network Indicators
    - Web Content Filtering

  <img width="1467" height="1006" alt="image" src="https://github.com/user-attachments/assets/cd132687-9069-42bc-97ee-285910286be8" />
  

---

# Importing the Policies

The policies contained in this repository are designed to be imported using **MickeM's Intune Management Tool**.

## IMPORTANT - AppControl 

App Control Managed Installer policy can't be improted as .json and needs to be setup manually, set it up before deploying App Control policy to your devices. Remember to double check that IME - Intune Managed Extension is installed on device, before enforcing policy for AppControl otherwise it wouldn't work. If it's not installing IME extension with Installer policy, than try to deploy an win32 app first

<img width="961" height="725" alt="image" src="https://github.com/user-attachments/assets/ff2e8d6c-fc16-470c-a6f0-ba99ba99d2e6" />

## Blocking All Non-Microsoft Websites

Once Defender for Endpoint and Cloud App integration is setup and you have device group in Defender go to Cloud Apps-> Cloud Apps Catalog --> Select All Gen AI and other AI apps , exclude non MS apps by tagging NON MS apps as Microsoft and than create a filter like on last picture

<img width="1805" height="1231" alt="image" src="https://github.com/user-attachments/assets/5d4366ae-b55c-4725-afe9-8e8fc2e53c8d" />

<img width="744" height="349" alt="image" src="https://github.com/user-attachments/assets/2d662bf3-17ef-42c0-ba4f-17c7769b9785" />

Than choose Select ALl and Tag them as Unsanctioned and select Device Group

## Blocking known proxies

In Settings -> Endpoint -> Web Content Filtering create a pplicy to Block "Illegal software", Illegal Software category contains well known proxies
<img width="1225" height="1202" alt="image" src="https://github.com/user-attachments/assets/d924548f-3f52-46b5-9bbc-3d7c89c68900" />


## Blocking 3 party Teams apps

Go to https://admin.teams.microsoft.com/policies/manage-apps
Actions -> Org wide setings 
<img width="1667" height="555" alt="image" src="https://github.com/user-attachments/assets/931d6098-318d-4108-8069-eb5768cc732b" />

Choose this setting and save 

<img width="364" height="862" alt="image" src="https://github.com/user-attachments/assets/717d7b80-ca5c-4947-a349-a73ffe08cd32" />

