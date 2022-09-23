<p>This script is "as is" and no further support may be guaranteed. You may use it as you wish, but do not expect support. You may request features, but this is just an upload based upon work I acctualy do in my work. This script has only been tested so far with Dell Optiplex, but based upon documentation from Dell, it will most likely work with other model serieses aswell. We're going to test it with the Latitude series very soon. For further bios settings you may set with this script see the <a href="https://dl.dell.com/content/manual25451988-dell-command-configure-version-4-7-user-s-guide.pdf?language=en-us&ps=true">Dell Command Configure documentation</a>, you'll mostly just need to copy other settings found in the powershell script in this repository and modify the settings to set. Please have an look through of the script before running, so that you know what are being set.</p><br><br><br><br><br><br><br><br><ul><li>Create an group of operations to perform during an deployment and add an WMI filter to filter out all dell computers (Select * From Win32_ComputerSystem WHERE Manufacturer LIKE "%DELL%")</li></ul>
<img src="https://raw.githubusercontent.com/nessnah/Dell-Bios-Computer-Deployment-Settings/main/ReadMe_Images/image.png"><ul><li>Install the attached app (Dell Command Configure). It is an MSI package so that it is sufficent with MSIEXEC /i DCC.msi /Quiet. Just remeber to check the box for an restart after the application has been installed. All the extra files beside the MSI package are nessecary for the install.</li><li>Modify the attached powershell script so that it suits your deployments. Ex. that it writes files to an area where your deployment service account has access (Ex. an additional folder in your deployment share)</li><li style="display:block">The script only uses A-Z, a-z and some special characters, you may take a look at the function for password generation for what special characters it uses.</li><li>Save the script somewhere your deployment may find it and add it as a part of your deployment after the install of DCC.</li></ul><div>Please do a dry run by hashtaging the commands for cctk.exe --SetupPwd and cctk.exe --SysPwd to check that it acctually creates the files with the passwords.</div><div><br aria-hidden="true"></div><div>When using this script, if you'd like to change the complexity of the passwords, change at the "Get-RandomPassword" command after defining the variables at lines 46 and 47. The numbers are repesented according to this: Length, How many upper characters you'd like, how many lower characters you'd like, how many numbers you'd like and at last how many special characters you'd like.</div><div><br aria-hidden="true"></div><div><br aria-hidden="true"></div></div>


Code:
https://user-images.githubusercontent.com/35728885/191994450-e722ee7c-828c-4743-8c4d-c7723bc4bf50.png

