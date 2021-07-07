# Windows Installation Instructions

We will be using WSL2 as official development environment on Windows 10. WSL2 is fast, reliable and efficient. Generally, we will recommend you using WSL2 for the purpose of software programming for astronomy.

As PHOEBE cannot build and run on windows natively *yet*, therefore we will be using WSL2 to setup a linux environment in Windows 10 to run PHOEBE on it. Also, installing WSL2 won't delete or replace your windows so rest assured.

## Install WSL2

You will find the detailed installation instrucions here: https://docs.microsoft.com/en-us/windows/wsl/install-win10

---

## Note ##

1. In the simplified install section of the above link, windows will install Ubuntu by default. To change that you can do:

        wsl --install -d <Distribution Name>
    
For our purpose, preferred would be Ubuntu 20.04

2. When using WSL2, do not use space while naming your folder or files instead use underscore instead of space. For ex. instead KSP EB, do KSP_EB. Linux isn't good with space in file paths and hence gives critical errors. 
---

## Running GUI apps on WSL2

Also, to run GUI apps (such as gedit, etc.) you will require install x-server on your system. Now, there are two ways you can achieve that.

1. Updating your Windows to windows insider preview build to run GUI apps natively on WSL2. Instructions: https://docs.microsoft.com/en-us/windows/wsl/tutorials/gui-apps
2. Using a third-party software such as xming, xserver, etc. Recommended one is **X410** but you are free to use any xserver provided it works smoothly.
    
  (i) Installation link of X410 (Note: Altough it's a paid software, we will use the trial version. It would last easily for 2 months.): https://www.microsoft.com/store/apps/9nlp712zmn9q 
  
  (ii) Setup link for X410 on WSL2: https://x410.dev/cookbook/wsl/using-x410-with-wsl2/  

---

### Once you are done with these steps return to the main instrutions [here](Install.md).
