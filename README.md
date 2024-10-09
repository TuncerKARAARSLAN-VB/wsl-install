Power shell is already installed on the server.

PowerShell is a command line tool that can run on both Windows and Linux. A Linux environment can be provided on Windows using the Windows Subsystem for Linux (WSL). PowerShell can be used to access and manage this WSL environment.

Now let's see how to install wsl before windows 11.

# Windows 10 WSL Installation

WSL (Windows Subsystem for Linux) can also be installed on systems prior to Windows 11. WSL has been supported since Windows 10, allowing you to run a Linux distribution on it. However, with Windows 11, a more advanced version of WSL, known as WSL 2, became available.

**Installing WSL on Windows 10:**

1. **Enabling Windows Features:**
   - Go to the "Turn Windows Features on or off" menu and enable the **"Windows Subsystem for Linux"** option. If you want to use WSL 2, also enable the **"Virtual Machine Platform"** option.

2. **WSL Installation Command:**
   - Run Command Prompt (CMD) or PowerShell as an administrator and enter the following command:
     ```
     wsl --install
     ```
   This command installs WSL and offers you a choice of Linux distributions.

3. **Upgrading to WSL 2 (Optional):**
   - By default, Windows 10 comes with WSL 1. To upgrade to WSL 2, your Windows version must be 1903 or newer. To switch to WSL 2, use the following command:
     ```
     wsl --set-default-version 2
     ```

**Important Notes:**
- WSL is not available on Windows 7 and Windows 8, so it's not possible to run a native Linux subsystem on these operating systems.
- WSL 2 runs a Linux kernel in a virtual machine, offering better performance and more features, but WSL 1 is also sufficient for lightweight tasks.

# Windows 11 and WSL

In Windows 11, you don't need to manually install WSL (Windows Subsystem for Linux) because it comes pre-installed. However, to start using WSL, you may need to download and enable a Linux distribution. This process is quite simple.

**WSL Setup on Windows 11:**

1. **Enabling WSL:**
   - Open Command Prompt (CMD) or PowerShell as an administrator and enter the following command:
     ```
     wsl --install
     ```
   This command installs WSL and by default downloads the latest version, WSL 2, along with a Linux distribution.

2. **Choosing a Linux Distribution:**
   - If you prefer, you can download different Linux distributions (Ubuntu, Debian, Fedora, etc.) from the Microsoft Store.

3. **Updating WSL (Optional):**
   - If WSL is already installed, you can run this command to update to the latest version:
     ```
     wsl --update
     ```

Since Windows 11 uses WSL 2 by default, no additional steps are necessary. The above steps are enough to start and use WSL.

# Windows Server 2022 and WSL

Installing WSL (Windows Subsystem for Linux) on Windows Server 2022 is possible, but WSL does not come pre-installed. You need to install it manually, and certain features must be enabled to use WSL 2.

**Steps to Install WSL on Windows Server 2022:**

1. **Enable WSL Features:**
   - First, open the "Turn Windows Features On or Off" menu and enable **"Windows Subsystem for Linux"** and **"Virtual Machine Platform"**.
   - Alternatively, you can enable these features via PowerShell:
     ```powershell
     dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
     dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
     ```

2. **Install WSL:**
   - Open PowerShell or Command Prompt (CMD) as an administrator and enter the following command:
     ```bash
     wsl --install
     ```
   This command installs WSL and by default downloads the latest WSL 2 version.

3. **Install a Linux Distribution:**
   - Since Microsoft Store is not available by default on Windows Server, you may need to manually install a Linux distribution. You can install Ubuntu via PowerShell with this command:
     ```bash
     wsl --install -d Ubuntu
     ```

4. **Set WSL 2 as Default (Optional):**
   - Windows Server 2022 comes with WSL 1 by default. To switch to WSL 2, use the following command:
     ```bash
     wsl --set-default-version 2
     ```

5. **Update WSL:**
   - If WSL is already installed, you can update it to the latest version using:
     ```bash
     wsl --update
     ```

**Important Note:**
- To use WSL 2 on Windows Server 2022, virtualization features like **Hyper-V** and **Virtual Machine Platform** must be enabled.

# Windows Server 2019 and WSL

On **Windows Server 2019**, WSL (Windows Subsystem for Linux) **can be installed** but only WSL 1 is available. WSL 2, which offers significant performance improvements and full Linux kernel compatibility, is not supported on Windows Server 2019. If you need basic Linux functionality, WSL 1 should be sufficient, but for more advanced features, upgrading to a newer version like **Windows Server 2022** is recommended.

### How to Install WSL on Windows Server 2019:

1. **Enable WSL** using PowerShell:
   - Open PowerShell as Administrator and run:
     ```powershell
     dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
     ```
2. **Reboot** your system.
3. **Install a Linux distribution**:
   - Once WSL is enabled, you can manually download and install Linux distributions. Note that the **Microsoft Store is not available** on Windows Server 2019, so you'll need to install distributions manually from other sources (like downloading from the internet and using `.appx` packages).

### Do You Need to Install WSL?
You only need to install WSL on Windows Server 2019 if you require Linux tools or a Linux environment. For tasks like development, running scripts, or using Linux-based tools, WSL 1 will allow basic Linux functionality. However, if you need more advanced Linux features or better performance, upgrading to **Windows Server 2022** and using **WSL 2** is advisable. 

If WSL isn't essential to your workflow, you might not need to install it.