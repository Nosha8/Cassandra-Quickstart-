<!DOCTYPE html>
<html>
<body>

<h2>System Requirement Sebelum Coba Cassandra Quickstart</h2>

<ul>
  <li>Download Docker Desktop Pada Link Berikut dan ikuti step instalasi : https://docs.docker.com/desktop/install/windows-install/</li><br>
  <li>Download WSL version2 : https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
  <br> How to Install WSL Ver2 : https://www.youtube.com/watch?v=n-J9438Mv-s</li><br>
  <li>Install VIM untuk edit dan check file di PowerShell atau CMD :
  		<br>1. Download the VIM executable for Windows from the official VIM website: https://www.vim.org/download.php
        <br>2. Extract the downloaded archive to a directory on your computer, for example: "C:\VIM" 
        <br>3. Add the VIM executable to your system's PATH environment variable: 
        <br>4. Open the Start menu and search for "Environment Variables"
        <br>Step1: Click on "Edit the system environment variables"
        <br>Step2: Click on the "Environment Variables" button
        <br>Step3: Under "System Variables", scroll down and find the "Path" variable, then click on "Edit"
        <br>Step4: Click on "New" and add the path to the VIM executable, for example: "C:\VIM"
        <br>Step5: Click "OK" to close all open dialog boxes
        <br/>5. Open a new Command Prompt window and type "vim" to test that the installation was successful.<br> <br>
         <li> Pastikan Feature Windows tertentu dalam keadaan "checklist"
         <br>Pada Search bar ketik "Turn Windows Feature on of off" dan klik.
         <br>Step1: Virtual Machine Platform --> Ubah ke Checklist
         <br>Step2: Windows Hypervisor Platform --> Ubah ke Checklist
         <br>Step3: Windows subsystem for linux --> Ubah ke Checklist</li>
        </li><br>
        <li>Pastikan Memory integrity menyala. 
  <br>Pada search bar ketik "Core Isolation"
      <br>Step1: Pada bagian Memory Integrity klik menjadi "On"
      note: apabila terkendala driver perlu di uninstall atau driver di update </li><br>
      <li> Simpan file data.cfg pada default directory saat membuat PowerShell. --> Lokasi file pada Prerequisites Resource dengan nama "data.cfg"</li>
</ul>  
