# CrackingthePerimeter
Useful scripts for gaining internal access through external perimeters

Requirements:

- Microsoft Online Services Sign-in Assistant
- The MSOnline module

Installation:

Install the 64-bit version of the Microsoft Online Services Sign-in Assistant: https://go.microsoft.com/fwlink/p/?LinkId=286152
Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:
- Open an elevated Windows PowerShell command prompt
- Run this command: Install-Module MSOnline
- If prompted to install the NuGet provider, type Y and press ENTER.
- If prompted to install the module from PSGallery, type Y and press ENTER.

Usage:
- \o365-spray.ps1 -Password Summer2018! -UserList .\userlist.txt

Basic Enumeration:
- host -t mx domain.com
- domain.com is handeled by 0 domain-com.mail.protection.outlook.com indicates o365 usage
- https://login.microsoftonline.com/getuserrealm.srf?login=user@domain.com&xml=1
- dig TXT domain.com and look if "v=spf1 include:spf.protection.outlook.com -all" which means if SPF is not good it will hardfail (-all)
