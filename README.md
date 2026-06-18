# ExternalAIHardeningBaseline
External AI hardening baseline for Windows 11

# Prerequisites

Before importing the policies in this repository, ensure your Microsoft 365 environment meets the following requirements.

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

## Download

Clone or download the tool from:

https://github.com/Micke-K/IntuneManagement

## Import Steps

1. Download and start **Intune Management Tool**.
2. Connect the tool to your Microsoft tenant.
3. Import the policies from this repository.
4. Review the imported policies.
5. Assign the policies to the appropriate users or devices.
6. Verify that the deployment completes successfully.

---

# Verification

After deployment, verify that:

- Devices are successfully onboarded to Microsoft Defender for Endpoint.
- Policies are successfully deployed from Intune.
- Microsoft Defender for Cloud Apps integration is active.
- Web Content Filtering is working as expected.
- Custom Network Indicators are applied successfully.

---

# Recommendations

- Test the deployment in a lab or pilot group before deploying to production.
- Verify all prerequisite integrations before importing the policies.
- Keep Microsoft Defender and Microsoft Intune connectors healthy before assigning policies.
