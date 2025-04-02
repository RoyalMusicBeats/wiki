# Setting Up a Windows Deployment Services (WDS) Server

Windows Deployment Services (WDS) is a Microsoft server technology used for network-based installation of Windows operating systems. This guide will walk you through the steps to set up a WDS server.

## Prerequisites

Before setting up WDS, ensure the following:
- A Windows Server machine with the WDS role installed.
- Active Directory, DHCP, and DNS configured in your environment.
- A Windows installation image (e.g., `.wim` file).

## Steps to Set Up WDS

### 1. Install the WDS Role
1. Open **Server Manager**.
2. Click on **Add roles and features**.
3. Select **Windows Deployment Services** under the **Server Roles** section.
4. Complete the wizard and restart the server if prompted.

### 2. Configure WDS
1. Open the **Windows Deployment Services** console.
2. Right-click on the server name and select **Configure Server**.
3. Follow the wizard:
    - Choose **Integrated with Active Directory**.
    - Specify the location for the Remote Installation Folder.
    - Configure PXE Server settings (e.g., respond to all client computers).

### 3. Add Boot and Install Images
1. In the WDS console, expand the server node.
2. Right-click **Boot Images** and select **Add Boot Image**.
    - Browse to the `boot.wim` file from your Windows installation media.
3. Repeat the process for **Install Images** using the `install.wim` file.

### 4. Configure DHCP (if needed)
If WDS and DHCP are on the same server:
- Configure DHCP to include option 66 (PXE server name) and option 67 (boot file name).

### 5. Test the Deployment
1. Boot a client machine via PXE.
2. Follow the on-screen instructions to install the operating system.

## Additional Resources
- [Microsoft WDS Documentation](https://learn.microsoft.com/en-us/windows-server/administration/windows-deployment-services/)
- [Troubleshooting WDS](https://learn.microsoft.com/en-us/windows-server/administration/windows-deployment-services/troubleshooting)

By following these steps, you should have a fully functional WDS server ready for network-based OS deployments.