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

## 3. Enter the Password


## 4. Save as Bat File
## 5. Convert Bat File to Exe
