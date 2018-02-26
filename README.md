# Folder-Locker
With this few simple steps you can lock your private information with a password in WIndows

## 1. Install editv64/32
Extract editv30.zip. After extraction you can see these files

![image](https://user-images.githubusercontent.com/36832858/36655846-7da23fa2-1b08-11e8-8f9f-274bd9ffb37e.png)

Now depending on the Windows OS Copy the respective editv64/editv32 in C:\Windows\System32\ (My System is Windows 64)

![image](https://user-images.githubusercontent.com/36832858/36655967-458420bc-1b09-11e8-8461-a908ab5585fb.png)

## 2. Copy Code
Before starting the code create a Folder where you want to save all your password protected files. (I'll recommend to create a folder which is not in C drive ). Once done open the folder and create a New Text Document in the folder
![image](https://user-images.githubusercontent.com/36832858/36656156-49924e62-1b0a-11e8-8b45-798bce6fe48a.png)

Rename the New Text Document to Locker
![image](https://user-images.githubusercontent.com/36832858/36656173-6240f26a-1b0a-11e8-99bf-a860035ec0ff.png)


```
cls

@ECHO OFF

title Folder Locker

if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK

if NOT EXIST Locker goto MDLOCKER

:CONFIRM

echo Are you sure u want to Lock the folder(Y/N)

set/p "cho=>"

if %cho%==Y goto LOCK

if %cho%==y goto LOCK

if %cho%==n goto END

if %cho%==N goto END

echo Invalid choice.

goto CONFIRM

:LOCK

ren Locker "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"

attrib +h +s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"

echo Folder locked

goto End

:UNLOCK

echo Enter password to Unlock folder

editv64 -m -p "Enter master password : " password

if NOT %password%==YOUR_PASSWORD goto FAIL

attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"

ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" Locker

echo Folder Unlocked successfully

goto End

:FAIL

echo Invalid password

echo Try Again(Y/N)

set/p "cho=>"

if %cho%==Y goto UNLOCK

if %cho%==N goto End

:MDLOCKER

md Locker

echo Locker created successfully

goto End

:End
```

Copy the above code in the Locker.txt file

## 3. Enter the Password

![image](https://user-images.githubusercontent.com/36832858/36658883-d10a4056-1b15-11e8-90de-9e87f1e9575b.png)

Change the password to your requirements. I have changed it to admin

![image](https://user-images.githubusercontent.com/36832858/36658951-1702dec4-1b16-11e8-919f-635a870d9569.png)

## 4. Save as Bat File
Now save the file as Locker.bat. To do this make sure you can view file extenstions. And while saving select File->Save As-> All Files and save it as Locker.bat
![image](https://user-images.githubusercontent.com/36832858/36659034-71619a86-1b16-11e8-8193-8de7c5e0072d.png)

Now delete the Locker.txt file. You will be left with Locker.bat
![image](https://user-images.githubusercontent.com/36832858/36659161-d9156a04-1b16-11e8-8aeb-0125c7f1aefc.png)
## 5. Convert Bat File to Exe
Extract the file Bat_To_Exe_Converter.Zip and Install Bat_To_Exe_Converter_(Installer).exe in the zip file. Make sure to create a desktop shortcut while installing. Once the installation is complete open the software.
![image](https://user-images.githubusercontent.com/36832858/36659435-cea361b0-1b17-11e8-9626-c9059a40fd79.png)

Open the locker.bat file. You will see the code in the window
![image](https://user-images.githubusercontent.com/36832858/36659529-20aadb00-1b18-11e8-8da0-a9aae9c47c9b.png)

Now change the Exe-Format depending upon your Windows Machine 64/32 | Console Application (Visible)
![image](https://user-images.githubusercontent.com/36832858/36659624-6a80e170-1b18-11e8-99e3-f01c2cf00708.png)

In my case it was 64. Now click the Convert Button in the menu (It Has gear as an icon). A window wil pop up to write down the name of the application. In my case I am naming it as Locker.exe
![image](https://user-images.githubusercontent.com/36832858/36659741-cfa6f06c-1b18-11e8-991e-cd3fe31f6c8a.png)

### Once completed.Close the application. And delete the Locker.bat

## 6. Running the Application
When you run the application for the first time it will create a New Folder name Locker. You can copy all the neccessary files which you want to password protect. Once moving of your files is done.
![image](https://user-images.githubusercontent.com/36832858/36659917-803fa9c8-1b19-11e8-8c2b-9e4863a629c8.png)

Run the application Again it will ask for Locking the folder. Select Y. Once selected the Folder will be Locked.
![image](https://user-images.githubusercontent.com/36832858/36659945-96b836b6-1b19-11e8-891e-354343988b5c.png)

To Open the folder you need to run the application and provide with the password which was set in Step 3.


### Enjoy !!!







