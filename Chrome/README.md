# Chrome

[Group Policy Object](./Chrome/Group Policy Objects/Computer/) and [Group Policy template files](./Chrome/Group Policy Template/) for the Chrome browser. The Group Policy template files typically change when a major version of Chrome is released but not all major releases change the templates. A file diffing tool can be used to determine if changes were made to the templates between major Chrome releases. The templates are provided as a convenience and may not always be updated to the templates that correspond to the latest major Chrome release.

## Updating the Chrome Group Policy templates

The latest version of the Group Policy template files can be downloaded from http://dl.google.com/dl/edgedl/chrome/policy/policy_templates.zip The VERSION file inside the zip file should match the latest version listed at http://omahaproxy.appspot.com/win Once the zip file has been extracted, copy the following files:
* \windows\admx\chrome.admx
* \windows\admx\en-us\chrome.adml


Those Group Policy template files need to be copied to specific a location on the file system. The location to copy the files to varies depending on if it is a domain versus a standalone system.

### Updating the Chrome Group Policy templates for a domain 

If the domain administrators have configured a [Group Policy Central Store](https://support.microsoft.com/en-us/kb/929841) for the domain, then copy the **chrome.admx** file to **\\\\_Fully Qualified Domain Name_\SYSVOL\\_Fully Qualified Domain Name_\Policies\PolicyDefinitions\\** and copy the **chrome.adml** file to **\\\\_Fully Qualified Domain Name_\SYSVOL\\_Fully Qualified Domain Name_\Policies\PolicyDefinitions\en-us\\**


If the domain administrators have **not** configured a Group Policy Central Store for the domain, then copy the **chrome.admx** file to **%SystemRoot%\PolicyDefinitions\\**, typically **C:\Windows\PolicyDefinitions\\**, and copy the **chrome.adml** file to **%SystemRoot%\PolicyDefinitions\en-us\\** folder on the domain controller.

## Updating the Chrome Group Policy templates for a standalone system 

**%SystemRoot%\PolicyDefinitions\\**, typically **C:\Windows\PolicyDefinitions\\**, contains Group Policy templates used by Local Group Policy on a standalone system. Copy the **chrome.admx** file to **%SystemRoot%\PolicyDefinitions\\** and copy the **chrome.adml** file to **%SystemRoot%\PolicyDefinitions\en-us\\** folder on the domain controller.


# Google Update
Chrome uses Google Update to update to the latest version. The Group Policy template file for Google Update can be downloaded from http://dl.google.com/update2/enterprise/GoogleUpdate.adm

# Acquire Googe Chrome
Download the enterprise version of Google Chrome:
* [X86](https://dl.google.com/edgedl/chrome/install/GoogleChromeStandaloneEnterprise.msi)
* [X64](https://dl.google.com/edgedl/chrome/install/GoogleChromeStandaloneEnterprise64.msi)


The version number of Chrome the download represents is available at http://omahaproxy.appspot.com/win

# Guidance
IAD has a security guide for Chrome called [Deploying and Securing Google Chrome in a Windows Enterprise](https://www.iad.gov:8443/iad/library/ia-guidance/security-configuration/applications/deploying-and-securing-google-chrome-in-a-windows-enterprise.cfm).