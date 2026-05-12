<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/github.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
<script>hljs.highlightAll();</script>

<style>
body {
  orphans: 2;
  widows: 2;
}

h1 {
  color: #1a1a2e;
  border-bottom: 2px solid #1a1a2e;
  break-after: avoid;
}

h2 {
  color: #16213e;
  border-bottom: 1px solid #dee2e6;
  break-after: avoid;
}

h3 {
  color: #0f3460;
  break-after: avoid;
}

h1 + *, h2 + *, h3 + * {
  break-before: avoid;
}

blockquote {
  border-left: 4px solid #0f3460;
  background-color: #f0f4f8;
  padding: 8px 12px;
  break-inside: avoid;
}

table {
  border-collapse: collapse;
  width: 100%;
  break-inside: auto;
}

tr {
  break-inside: avoid;
  break-after: auto;
}

th {
  background-color: #1a1a2e;
  color: white;
}

td, th {
  border: 1px solid #dee2e6;
  padding: 8px;
}

/* INLINE CODE */

code {
  background-color: #f0f4f8;
  padding: 2px 4px;
  border-radius: 3px;
  font-family: 'Courier New', monospace;
  font-size: 0.9em;
  color: #14532d !important;
  font-weight: 600;
}

/* CODE BLOCKS */

pre {
  background-color: #f6f8fa;
  border: 1px solid #dee2e6;
  border-radius: 6px;
  padding: 16px;
  overflow-x: auto;
  break-inside: auto;
  white-space: pre-wrap;
  word-wrap: break-word;
}

pre code {
  background-color: transparent;
  padding: 0;
}

/* PDF FRIENDLY SYNTAX COLORS */

.hljs {
  color: #14532d !important;
}

.hljs-string {
  color: #d97706 !important;
}

.hljs-attr,
.hljs-keyword,
.hljs-property {
  color: #0ea5e9 !important;
}

.hljs-number,
.hljs-literal,
.hljs-boolean {
  color: #059669 !important;
}

.hljs-punctuation {
  color: #6b7280 !important;
}
</style>

# Visual Studio Code Installation Guide

---

| **FIELD**       | **DETAILS**              |
|-----------------|--------------------------|
| Product         | Visual Studio Code (VS Code)|
| Document Type   | Installation Guide       |
| OS/Platform     | Windows                  |
| Version         | `1.109.5`                |
| Author          | Gokul S Anand            |
| Last Updated    | May 12, 2026             |

---

## Introduction

Visual Studio Code (VS Code) is a code editor developed by Microsoft. This guide helps users to successfully download, install, verify, and uninstall it on Windows.

## Table of Contents

1. Introduction

2. Who This Guide Is For

3. System Requirements

4. Prerequisites

5. Downloading VS Code

6. Installation Steps

7. Post-Installation Setup

8. Verifying the Installation

9. Uninstallation

10. Troubleshooting

11. FAQ

12. Support & Contact

13. License & Compliance

## Who This Guide Is For

This guide is intended for:

- Software Developers and IT Support Teams looking to install VS Code on their Windows for the first time.

- Beginners with basic computer knowledge looking to install VS Code on their Windows.

## System Requirements

| **Component**   | **Minimum**      | **Recommended**  |
|-----------------|------------------|------------------|
| OS              | Windows 10 (64-bit) | Windows 11 (64-bit)|
| RAM             | 4 GB             | 8 GB             |
| Disk Space      | 850 MB           | 1 GB             |
| Processor       | ARM64 or x64     | Quad-core or better |
| Internet        | Required for setup | Stable broadband |

> 📝 **Note:** Recommended specifications are based on general best practices. Official minimum requirements sourced from `code.visualstudio.com/docs/supporting/requirements`

---

## Prerequisites

- [ ] Administrator access

- [ ] Your system meets the minimum system requirements

- [ ] Stable internet connection

- [ ] Any previous version of VS Code is uninstalled (for a clean installation)

---

## Downloading VS Code

### Step 1: Visit the official website of VS Code

Go to the official website of VS Code: `https://code.visualstudio.com/`

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-01-download.png" width="500px" />

> ⚠️ **Warning:** Always download from the official website only. Avoid third-party download sites.

### Step 2: Download the installer file for Windows

Click **Download for Windows**; wait for the download completion. 

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-02-download.png" width="500px" />

> 💡 **Tip:** Note where the file is downloaded -
> you will need it in the next step.

**Expected Result:** The installer file of VS Code is downloaded without any errors. 

---

## Installation Steps

### Step 1: Open the downloaded file location

Open the **Downloads folder** in your Windows.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-01-install.png" width="500px" />

### Step 2: Start the installation process

Double click `VSCodeUserSetup-x64-1.109.5`

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-02-install..png" width="500px" />

### Step 3: Accept the License Agreement

Click **I accept the agreement** after reading the License agreements > click **Next**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-03-install.png" width="500px" />

> ⚠️ **Warning:** You must accept the agreement to proceed with installation.

### Step 4: Select the Installation Folder

Select the folder to which you want the VS Code to be installed > **Next**

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-04-install.png" width="500px" />

> 💡 **Tip:** Keep the default folder unless you have a specific reason to change it.

### Step 5: Choose Menu Folder

Choose the **Start Menu Folder** > click **Next**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-05-install.png" width="500px" />

### Step 6: Select Additional Task

Tick the **Create a desktop icon** > **Next**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-06-install.png" width="500px" />

> 💡 **Tip:** Also tick **Add to PATH** option — this allows you to open VS Code from the terminal directly.

### Step 7: Install

Click **Install** and wait for it to be completed.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-07-install.png" width="500px" />

### Step 8: Complete the Installation

Click **Finish** to complete the installation. VS Code launches automatically. 

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-08-install.png" width="500px" />

**Expected Result:** VS Code is installed on the system without any errors.

---

## Post-Installation Setup

### Step 1: Change the Color Theme

1. Click the **Settings Icon** on the left bottom > **Themes** > **Color Theme** (**Ctrl+K Ctrl+T**)

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-1.1-post-install.png" width="500px" />

2. Select the theme you prefer from the given options.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-1.2-post-install.png" width="500px" />

> 💡 **Tip:** Changing the color theme to dark is easier on the eyes during long coding sessions.

**Expected Result:** The color theme of VS Code is changed without any errors.

### Step 2: Sign in to VS Code

1. Click on the **Profile icon** on the bottom left > **Sign in to use AI features**

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-2.1-post install.png" width="500px" />

2. Choose a method to sign in; provide the credentials asked by the method you choose.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-2.2-post-install.png" width="500px" />

**Expected Result:** Successfully signed in to VS Code.

### Step 3: Install Extensions

1. Click on the **Extension icon** (**Ctrl+Shift+X**) on the **Left side bar**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-3.1-post-install.png" width="500px" />

2. Search for the extension you want > click **Install**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-3.2-post-install.png" width="500px" />

**Expected Result:** Extension is installed without any errors.

---

## Verifying the Installation

- [ ] Confirm VS Code opens without any errors

- [ ] Verify the version is correct: Open VS Code > click **Help** > **About**

- [ ] Ensure basic features like creating new files, extensions, terminals, and settings work properly

**Expected Result:** VS Code is installed and functioning correctly on your Windows system.

---

## Uninstallation

### Windows

1. Open **Start menu** > search **Control Panel** > click **Open**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-01-uninstall.png" width="500px" />

2. Click on **Programs** > **Programs and Features**

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-02-uninstall.png" width="500px" />

3. Search **Microsoft Visual Studio Code**.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-03-uninstall.png" width="500px" />

4. Click on the **VS Code app icon** > Choose **Yes** for the uninstall confirmation pop-up.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-04-uninstall.png" width="500px" />

5. Wait for the uninstallation to get completed > Click **Ok** for the confirmation.

&nbsp;&nbsp;&nbsp;&nbsp;<img src="C:/TWR Gokul/Office/IMAGES/vs/step-05-uninstall.png" width="500px" />

**Expected Result:** VS Code is uninstalled from Windows without any errors.

---

## Troubleshooting

### Issue 1: Installing fails

**Cause:**  

- Insufficient storage 

- The system doesn't meet the minimum requirements for the installation

- Corrupted Installer file

**Fix:**  

1. Ensure your system has enough storage for the installation. If not, delete some unwanted files.

2. Verify your system meets the minimum requirements listed in the System Requirements section above.

3. Confirm the installer file is of the latest version. If not, download the latest installer file from the official website.

4. Attempt the action again.

> ⚠️ **Warning:** Do not interrupt the installation process once it has started.

**Expected Result:** VS Code is successfully installed on Windows.

### Issue 2: Installing the extension fails

**Cause:**

- Unstable internet connection

- Insufficient storage space

- Permission for the extension is blocked in settings

- The app is outdated for the extension

**Fix:**  

1. Ensure a stable internet connection.

2. Confirm your system has enough storage space for the installation. If not, delete some unwanted files.

3. Make sure the type of extension you are trying to install is allowed. To check that, click the **settings icon** > **Settings** > search **Extension** > confirm the type of extension is allowed.

4. Check whether the type of extension runs on your current app version. If not, update VS Code by clicking **Help** > **Check for Updates** and installing available updates.

**Expected Result:** The extension is successfully installed.

### Issue 3: Unable to Uninstall

**Cause:**

- VS Code is still running in the background.

- Insufficient administrator permissions.

**Fix:**

1. Open **Task Manager** (**Ctrl+Shift+Esc**) and end any running VS Code processes.

2. Ensure you have administrator access on Windows.

3. Restart the system.

4. Attempt the uninstallation again.

**Expected Result:** VS Code is successfully uninstalled from Windows.

---

## FAQ

**Q1. Is VS Code free?**

**A:** Yes, VS Code is a free code editor, that runs on the macOS, Linux, and Windows operating systems.

**Q2. How to update the app?**

**A:** By default, VS Code automatically updates when new versions are released. To disable auto-updates, go to **File** > **Preferences** > **Settings** > search **Update: Mode** > change it from **default** to **none**.

**Q3. Can I control which extensions are allowed to be installed?**

**A:** Yes, by default, all extensions are allowed. You can set this to allow only specific ones. You can filter by publisher, extension, version, or platform. Then, block the others. To do this, go to **Settings** (**Ctrl+,**) > **Extension settings**; set it as you prefer.  

## Support & Contact

| **CHANNEL**      | **DETAILS**                        |
|------------------|------------------------------------|
| Official Docs    | `https://code.visualstudio.com/docs` |
| Stack Overflow  | `https://stackoverflow.com/questions/tagged/vscode`     |
| FAQ & Support    | `https://code.visualstudio.com/docs/supporting/FAQ` |

---

## License & Compliance

This document was created for portfolio and educational purposes only.

Visual Studio Code is developed and maintained by Microsoft Corporation. All trademarks, logos, and product names belong to Microsoft Corporation.

VS Code is licensed under the MIT License.  
License details: `https://github.com/microsoft/vscode/blob/main/LICENSE.txt`

All product information in this guide is based on VS Code Version `1.109.5` for Windows.

This document is not affiliated with or endorsed by Microsoft Corporation.

---
---

*Document Version: 1.1 | Last Reviewed: May 12, 2026*

---