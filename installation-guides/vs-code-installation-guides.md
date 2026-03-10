# Visual Studio Code (VS Code) Installation Guide

---

| **FIELD**       | **DETAILS**              |
|-----------------|--------------------------|
| Product         | Visual Studio Code (VS Code)|
| Document Type   | Installation Guide       |
| OS/Platform     | Windows                  |
| Version         | 1.109.5                  |
| Author          | Gokul S Anand            |
| Last Updated    | March 3, 2026            |

---

## Introduction

Visual Studio Code (VS Code) is a code editor developed by Microsoft. This guide helps users to successfully download, install, verify and uninstall it on Windows.

## Who This Guide Is For

This guide is intended for:

- Software Developers and IT Support Teams installing VS Code on their Windows for the first time.

- Beginners with basic computer knowledge looking to install VS Code on their Windows.

## System Requirements

| **Component**   | **Minimum**      | **Recommended**  |
|-----------------|------------------|------------------|
| OS              | Windows 10 (64-bit) | Windows 11 (64-bit) |
| RAM             | 4 GB             | 8 GB             |
| Disk Space      | 850 MB           | 1 GB             |
| Processor       | ARM64 or x64     | Quad-core or better |
| Internet        | Required for setup | stable internet connections |

> 💡 **Note:** Recommended specifications are based on 
> general best practices. Official minimum requirements 
> sourced from code.visualstudio.com/docs/supporting/requirements

---

## Prerequisites

- [ ] Administrator access
- [ ] Your system meets the minimum system requirements
- [ ] Stable internet connection
- [ ] Any previous version of VS Code is uninstalled (for clean installation)

---

## Downloading VS Code

### Step 1: Visit the official website of VS Code

> ⚠️ **Warning:** Always download from the official 
> website only. Avoid third-party download sites.

Go to the official website of VS Code: https://code.visualstudio.com/

### Step 2: Download the installer file for Windows

Click **Download for Windows**; wait for the download completion. 

> 💡 **Tip:** Note where the file is downloaded -
> you will need it in the next step.

**Expected Result:** Installer file of VS Code is downloaded without any errors. 

---

## Installation Steps

### Step 1: Open the downloaded file location

Open **Downloads folder** in your Windows

### Step 2: Start the installing process

Double click `VSCodeUserSetup-x64-1.109.5`

### Step 3: Accept the License Agreement

Click **I accept the agreement** after reading the License agreements > click **Next**

> ⚠️ **Warning:** You must accept the agreement 
> to proceed with installation.

### Step 4: Select the Installation Folder

Select the folder to which you want the VS Code to be installed > **Next**

> 💡 **Tip:** Keep the default folder unless you 
> have a specific reason to change it.

### Step 5: Choose Menu Folder

Choose the **Start Menu Folder** > click **Next**

### Step 6: Select Additional Task

Tick the **Create a desktop icon** > **Next**

> 💡 **Tip:** Also tick **Add to PATH** option — 
> this allows you to open VS Code from the 
> terminal directly.

### Step 7: Install

Click **Install** and wait for it to be completed.

### Step 8: Complete the Installation

Click **Finish** to complete the installation. VS Code launches automatically. 
**Expected Result:** VS Code is installed on the system without any errors.

---

## Post-Installation Setup

### Step 1: Change the Color Theme

1. Click the **Setting Icon** on the left bottom > **Themes** > **Color Theme** (**Ctrl+K Ctrl+T**)

2. Select the theme you prefer from the given options.

> 💡 **Tip:** Changing the color theme to dark is easier on the eyes during long coding sessions.

**Expected Result:** Color theme of VS Code is changed without any errors.

### Step 2: Sign in to VS Code

1. Click on the **Profile icon** on the left bottom > **Sign in to use AI features**

2. Choose a method to sign in; provide the credentials asked by the method you choose.

**Expected Result:** Successfully signed in to VS Code.

### Step 3: Install Extensions

1. Click on the **Extension icon** (**Ctrl+Shift+X**) on the **Left side bar**

2. Search the extension you want > click **Install**

**Expected Result:** Extension is installed without any errors.

---

## Verifying the Installation

- [ ] Confirm VS Code opens without any errors.

- [ ] Verify the version is correct: Open VS Code > click **Help** > **About**

- [ ] Ensure basic features like Creating new file, Extension, Terminals, and Settings works properly.

**Expected Result:** VS Code is installed and functioning correctly on your Windows system.

---

## Uninstallation

### Windows

1. Open **Start menu** > search **Control Panel** > click **Open**

2. Click on **Programs** > **Programs and Features**

3. Search **Microsoft Visual Studio Code**

4. Click on the **VS Code app icon** > Choose **Yes** for the uninstall confirmation pop up.

5. Wait for the uninstalling to get completed > Click **Ok** for the confirmation 

**Expected Result:** VS Code is uninstalled from Windows without any errors.

---

## Troubleshooting

### Issue 1: Installing fails

**Cause:**  

- Insufficient storage 

- System doesn't meet the minimum requirements for the installation

- Corrupted Installer file

**Fix:**  

1. Ensure your system has enough storage for the installation. If not, delete some unwanted files.

2. Verify your system meets the minimum requirements listed in the System Requirements section above.

3. Confirm the installer file is of the latest version. If not, download the latest installer file from the official website.

4. Attempt the action again.

> ⚠️ **Warning:** Do not interrupt the installation 
> process once it has started.

**Expected Result:** VS Code is successfully installed on Windows.

### Issue 2: Installing Extension fails

**Cause:**

- Unstable internet connection

- Insufficient storage space

- Permission for the extension is blocked in settings

- App is outdated for the Extension

**Fix:**  

1. Ensure a stable internet connect

2. Confirm your system has enough storage space for the installing. If not, delete some unwanted files.

3. Make sure the type of extension you are trying to install is allowed. For checking that click **settings icon** > **Settings** > search **Extension** > confirm the type of extension is allowed

4. Check whether the type of extension runs on your current app version. If not, update VS Code by clicking **Help** > **Check for Updates** and install available updates.

**Expected Result:** The extension is successfully installed.

### Issue 3: Unable to Uninstall

**Cause:**
- VS Code is still running in the background
- Insufficient administrator permissions

**Fix:**
1. Open **Task Manager** (**Ctrl+Shift+Esc**) and 
   end any running VS Code processes
2. Ensure you have administrator access on Windows
3. Restart the system
4. Attempt the uninstallation again

**Expected Result:** VS Code is successfully 
uninstalled from Windows.

---

## FAQ

**Q1: Is VS Code free?**
**A:** Yes, VS Code is a free code editor, which runs on the macOS, Linux, and Windows operating systems.

**Q2: How to update the app?**
**A:** By default, VS Code automatically updates when new versions are released. To disable auto-updates, go to **File** > **Preferences** > **Settings** > search **Update: Mode** > change it from **default** to **none**.

**Q3: Can I control which extensions are allowed to be installed?**
**A:** Yes, by default, all extensions are allowed. You can set this to allow only specific ones. You can filter by publisher, extension, version, or platform. Then, block the others. To do this go to **Settings** (**Ctrl+,**) > **Extension settings**; set it as you prefer.  

## Support & Contact

| Channel          | Details  |
|------------------|----------|
| Official Docs    | https://code.visualstudio.com/docs |
| Community Forum  | https://stackoverflow.com/questions/tagged/vscode |
| FAQ & Support    | https://code.visualstudio.com/docs/supporting/FAQ |

---

## License & Compliance

This document was created for portfolio and educational purposes only.

Visual Studio Code is developed and maintained by Microsoft Corporation. All trademarks, logos, and product names belong to Microsoft Corporation.

VS Code is licensed under the MIT License.  
License details: <https://github.com/microsoft/vscode/blob/main/LICENSE.txt>

All product information in this guide is based on VS Code Version 1.109.5 for Windows.

This document is not affiliated with or endorsed by Microsoft Corporation.

---
---

*Document Version: 1.0 | Last Reviewed: [March 9, 2026]*
