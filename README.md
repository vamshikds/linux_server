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
3. Installing **SSH Key** to connect with VPS and your local laptop:
    - **Ed25519** is modern, secure, fast and current defacto recommended cryptographic key type for OpenSSH and shorter and quicker than RSA key type.
        - Run Dialog Box and press **Windows key + R** and type **`pwsh`** to open **PowerShell 7** or type **`powershell`** to open **Windows Powershell 5** 
        - use command **`-t`** for selecting key type (select one of these **`ed25519`** or **`rsa`** or **`ecdsa`** or **`dsa`**) and
        - use command **`-C`** for comment, the comment is only for your reference and not for security purpose.
        - type this command and enter: **`ssh-keygen -t ed25519 -C "your comment"`**
        - then it enter again to confirm the **.ssh folder** location, its best to keep the same and not to modify
        - then it pops it asks to enter a **passphrase**, its recommended to generate one like your password and then enter
        - then it generates the **key fingerprint** and **randomart image**
        - The default **Key Derivation Function (KDF)** rounds fore newer OpenSSH keys is often **16 rounds.**
            - A **Key Derivation Function (KDF)** is a cryptographic algorithm that acts like a highly specialized, ultra-secure recipe for turning one secret value into one or more new, stronger, and cryptographically safe secret keys.
            - KDF iterations means how difficult it is to get the key from your password. The purpose is to intentionally slow down brute-force attacks on your password, as an attacker would have to perform those 100 slow operations for every password guess.
            - to increase the KDF rounds we can use **`-a`** command and specifc the number of rounds like: **`ssh-keygen -t ed25519 -a 100`**, here the number of KDF rounds will be 100.
            - **`ssh-keygen -t ed25519 -a 256 -C "your comment"`** this generates a ed25519 key with 256 KDF counts
            - **`ssh-keygen -t ed25519 -a 100 -f testkey100 -N "testpass" -C "benchmark100"`** this will generate a key with 100 KDF counts with a filename testkey100 with a passphrase of testpass and comment benchmark100
            - **`Mearsure-Command { ssh-keygen -y -f testkey100 }`** this will measure the time taken to unlock the public key from a private key using **`ssh-keygen -y`** command.
    - to delete files via powershell:
        - **`rm yourfilename`** then press enter
        - before this check the number of files or sub-directories in your current directory by simple tying **`ls`** command and then enter.
4. Connecting with the server
    

  
