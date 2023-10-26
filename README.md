<h1>PowerShell Script to Automatically Populate Users in Active Directory</h1>

<h2>Description</h2>
This Powershell scripting project is to automate the process of adding hundreds and thousands of users into an Active Directory domain. I will explain through the lines of the script to detail the functions of each line. Enjoy! ^_^
<br />


<h2>Project Walk-Through</h2>

<p align="center">
To begin, you'll have to wrtite the script on Notepad and save the file as a PowerShell Script (.ps1). Here is the script as a text file: <br/>
<img src="https://i.imgur.com/1BVNAnf.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
Here's what the script looks like on Windows PowerShell ISE:  <br/>
<img src="https://i.imgur.com/fUszO6M.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
You should also have a separate text file prepared with a bunch of random names: <br/>
<img src="https://i.imgur.com/PGfEhb5.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
First, let's start with variables. The first one is $PASSWORD_FOR_USERS = "Password1". <br/>
  This line will automatically designate each user's password as "Password1":  <br/>
<img src="https://i.imgur.com/2AGaL8f.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The next variable is to insert the "Names.txt" file. The "Get-Content" command will pull the list of names in the <br/>
  "Names.txt" file and insert them into the variable, "$USER_FIRST_LAST_LIST":  <br/>
<img src="https://i.imgur.com/hyO6YKt.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The next variable is for Active Directory to mask the password (Password1) so that it is not left as plaintext:  <br/>
<img src="https://i.imgur.com/m8i5qDd.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
This line configures the creation of an Organizational Unit (OU):  <br/>
<img src="https://i.imgur.com/QUyPznn.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
It creates a new OU:  <br/>
<img src="https://i.imgur.com/0NETMUM.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
Named "_USERS":  <br/>
<img src="https://i.imgur.com/Ni80Htm.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
and checks off the "Protect container from accidental deletion" (please note that this was done for lab purposes in a safe environment):  <br/>
<img src="https://i.imgur.com/AV0mKFU.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The next line is to loop individual user settings, per user, meaning that the lists of code from lines 9 through 24 will run for each user.:  <br/>
<img src="https://i.imgur.com/S2dxMNi.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The whole process can be collapsed, using the curly brackets:  <br/>
<img src="https://i.imgur.com/xefASun.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The "$n" represents each user in the "Names.txt" file:  <br/>
<img src="https://i.imgur.com/S2dxMNi.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
This line will adjust the variable "$first" to be the first name:  <br/>
<img src="https://i.imgur.com/VZk0lbO.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
This line will adjust the variable "$last" to be the last name:  <br/>
<img src="https://i.imgur.com/sNzvfE6.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
This line will adjust the variable "$username" to create a username using the first letter of the first name <br/>
  and combine it with the last name (i.e. John Smith = jsmith):  <br/>
<img src="https://i.imgur.com/xj1tlWS.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
This line is how the output of the running script will appear on PowerShell:  <br/>
<img src="https://i.imgur.com/l00eBha.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The background color is set to "black" and the font color is set to "cyan":  <br/>
<img src="https://i.imgur.com/ysvzO7W.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
The next line is actually one line, divided into multiple lines. It will go through the process of adding a new user:  <br/>
<img src="https://i.imgur.com/2hpo8FG.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
Filling out the first and last name, user longon name:  <br/>
<img src="https://i.imgur.com/HHqyLUp.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Creating a default password (Premade variable $password), and checking the box "Password never expires":  <br/>
<img src="https://i.imgur.com/Yo52Bao.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
It will also automatically add the user into the newly created OU (_USERS):  <br/>
<img src="https://i.imgur.com/gG4J6si.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />
and enable the user to be an active account:  <br/>
<img src="https://i.imgur.com/dMEjJ7R.png" height="80%" width="80%" alt="ActiveDirectory_PowerShell"/>
<br />
<br />

<h2>Conclusion</h2>
This concludes writing the automating script of populating many users at once. All settings and variables can be adjusted to your matching environment and liking. As always, practice safe coding and password management! Please feel free to ask any questions.
