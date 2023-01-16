Link Step by Step Example : https://www.youtube.com/watch?v=HEG4cgTLJrA
1. Download Docker Desktop Pada Link Berikut dan ikuti step instalasi : https://docs.docker.com/desktop/install/windows-install/
2. Download WSL version2 : https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi 
  1. How to Install WSL Ver2 : https://www.youtube.com/watch?v=n-J9438Mv-s 
3. Install VIM untuk edit dan check file di PowerShell atau CMD : 
  1. Download the VIM executable for Windows from the official VIM website: https://www.vim.org/download.php
  2. Extract the downloaded archive to a directory on your computer, for example: "C:\VIM"
  3. Add the VIM executable to your system's PATH environment variable:
  4. Open the Start menu and search for "Environment Variables"
      -	Click on "Edit the system environment variables"
	    - Click on the "Environment Variables" button
  	  - Under "System Variables", scroll down and find the "Path" variable, then click on "Edit"
  	  - Click on "New" and add the path to the VIM executable, for example: "C:\VIM"
  	  - Click "OK" to close all open dialog boxes
  5. Open a new Command Prompt window and type "vim" to test that the installation was successful.
4. Pastikan Feature Windows Menyala
  1. Pada Search bar ketik "Turn Windows Feature on of off" dan klik.
      - Virtual Machine Platform --> Ubah ke Checklist
      - Windows Hypervisor Platform --> Ubah ke Checklist
      - Windows subsystem for linux --> Ubah ke Checklist
5. Pastikan Memory integrity menyala. 
  1. Pada search bar ketik "Core Isolation"
      - Pada bagian Memory Integrity klik menjadi "On"
      - note: apabila terkendala driver perlu di uninstall atau driver di update
6. Simpan file data.cfg pada default directory saat membuat PowerShell. --> Lokasi file pada Prerequisites Resource dengan nama "data.cfg"
