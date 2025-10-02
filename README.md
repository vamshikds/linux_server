# linux_server
Linux Server Admin via Windows 11

1. Go to terminal/command prompt by typing **`cmd`** in windows search or by clicking **`windows + R`** then entering **`cmd`** in the prompt.
    - in the Windows Terminal type **`winget`** to check the version of windows package manager - The winget command line utility enables installing applications and other packages from the command line.
    - WinGet (short for Windows Package Manager) is a free and open-source command-line package manager. It's a tool that allows one to easily discover, install, upgrade, and manage applications on the computer using simple text commands in the terminal.
    - Command prompt of winget is: **`winget [<command>] [<options>]`**
    - Search for Microsoft Powershell.
        - Type: **`winget search Microsoft.Powershell`**.
        - If prompted to agree to source terms, type **\<Y\>** to agree and continue.
        - Now install the powershell by typing: **`winget install --id Microsoft.PowerShell --source winget`**
        - It will install PowerShell.
        - Exit the Windows Terminal by typing **`Exit`** and then press **[enter]**
2. Now there will be two different, coexisting versions of PowerShells installed.
    -  **Windows PowerShell (Version 5.1):**
        -  This is the classic, built-in version of PowerShell that is pre-installed with Windows.
        -  The executable name is **`powershell.exe`**. When you type **"PowerShell"** or **`powershell.exe`** in the windows search, you are starting this version.
        -  To check its version simply type **`$PSVersionTable`** in the Windows Powershell terminal when you start it by using the above commands.
        -  The version listed will be 5.1.xxxxx.xxxx
        -  It is no longer actively developed for new features, only security patches.
    - **PowerShell (Version 7.x - formerly PowerShell Core):**
        - This is the modern, cross-platform version you installed using **`winget`** (version 7.5.x.x).
        - the executable name is **`pwsh.exe`**. To start this version simply type this in the windows search.
        - It installs side-by-side with Windows PowerShell 5.1, it does not replace it.
        - To check its version type **`pwsh --verion`** in either Windows Powershell or in Windows Terminal or even in the terminal which opens when you run **`pwsh.exe`** in the windows search.
        - The version listed will be 7.5.x.
        - It is actively developed and built on .NET.


  
