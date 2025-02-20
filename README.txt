Last Updated: 11/6/2019

This is the failsafe for the Network Rename Script.  This should be used after the Network Rename Script fails at least twice, tested with both a wifi and ethernet connection.  If this is the case, use this method. The reason this is the second option is that the script it runs has some undesirable behavior.  First, it installs the AD-Module on the local computer, which isn't inherently a bad thing, but it is not what we want to be doing on every computer we reimage.  It also requires more restarts than the network one, so it takes a lot longer on slower machines.   It has the benefit of almost always working if, at the bare minimum, Powershell is working, and the admin account has actual admin privileges.    It also changes the Local Admin password so that whoever is doing the rename only has to use a LAPS password the bare minimum amount of times.  

A) There are currently two ways to access the Local Rename Script: USB and the Ghost server.  Both require that you be logged into the local computer as the local administrator.   The USB should be in the cup in QA, but sometimes things get lost. Run the file called RunMeForRename.   If it's lost, you can go on the local computer and type \\ghostserver to bring up the ghost server. Theoretically, this should work anywhere on campus, but the range hasn't fully been tested.  Navigate to quartus/RenameScript, and run the file called RunMeForRename. This will start the rename script.  

B) Once the Rename script starts going, it will prompt you with choices ([Y] , [A], [N], etc.). Choose [A] twice and then [Y]. This will cause the computer to restart once.  

C) Remember that this rename script changes the local admin password to "thisisthepassword" (without quotes).  That way you don't have to log in using LAPS credentials every time, because they suck (Who uses O and 0 in the same password). 

D) Repeat step A), but this time when it ask for your credentials to access to the Ghost Server, put ' AD\(your username) ' {without the apostrophes}

E) It should start renaming it then it'll prompt you with some options

F ) Press [A] again and wait for it to restart.

G) Once the script is finished, AD will change the local admin password back to some LAPS password, so if "thisisthepassword" (without quotes) stops working, try LAPS and it should work.


NOTE:  If this doesn't work, please message me (Zach) either through teams or email (seefeldzd@msoe.edu), and let me know what doesn't work.  Either the code is bad or the solution is missing some information, just inform me of what doesn't work so I can make changes accordingly.  
