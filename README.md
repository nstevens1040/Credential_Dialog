# Credential_Dialog

.NET Framework library that invokes a standard Windows credential prompt

## Requirements

*   **Microsoft Windows** operating system

       (tested on **Windows 10** Version 1909 OS build 18363.720 and **Windows Server 2016** Version 1607 OS build 14393.3564)

*   **Windows PowerShell**, minimum version 3.0

       (tested PowerShell versions **3.0**, **5.1.14393.3471**, and **5.1.18362.628**. I have not tested PowerShell Core.)

## Installation

Open the SLN file in Visual Studio and build the library.  
Once you've done that, then you can:  
*   Add a reference to the DLL file and use in another solution. For example:  
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using WinCred;
namespace CredUIPrompt
{
    class Program
    {
        static void Main(string[] args)
        {
            List<string> creds = CredentialDialog.AuthEasy(args[0]);
            creds.ForEach((i) => { Console.WriteLine(i); });
        }
    }
}
```  
*   You can also use it in PowerShell like this:  
```ps1
Add-Type -Path "C:\path\to\source\repos\Credential_Dialog\Credential_Dialog\bin\debug\Credential_Dialog.dll"
[WinCred.CredentialDialog]::AuthEasy();
```
*   You can also pass a string argument so that the prompt will read: **"Enter your credentials to log onto: " + args[0]; **  
```ps1
Add-Type -Path "C:\path\to\source\repos\Credential_Dialog\Credential_Dialog\bin\debug\Credential_Dialog.dll"
[WinCred.CredentialDialog]::AuthEasy("Twitter.com");
```  
