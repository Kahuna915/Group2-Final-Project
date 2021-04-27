Prerequisites:

![image](https://user-images.githubusercontent.com/62860262/116321584-55189f80-a788-11eb-965b-eb8cf731e95b.png)

    > In Computers put W1 + W2 + UTIL
    > In Servers put MGMT
### Domain Group Policy that allows W1 + W2 to remote desktop between one another.
    > Open group policy
    > Right-click on the domain and select create GPO in this domain and link it here
    > Navigate to Computer configuration, to windows settings, to security settings, to windows firewall with advanced security, to windows firewall with advanced security, to inbound rules, and create a new rule
    > Select Port in the New Inbound Rule Wizard
    > Ensure TCP and Specific Local Port: 3389 
    > Allow the connection and select Domain and Private Profiles
    > Name The Rule
        > After this do:
            > Go to computer configuration, then policies, then administrative templates, then windows components, then remote desktop services, then remote desktop session host, and then connections
            > Select All users to connect remotely by using Remote Desktop Services to Enable
            > Go to computer configuration --> Policies --> Administrative Templates --> windows components --> Remote Desktop Services --> Remote Desktop Session Host --> Security and set require user authentication for remote connections by using network-level authentication to enable
    > Close out of the GPO and run a gpupdate /force
 
### Corporate wallpaper to W1 + W2 + MGMT1.
    > So for corporate wallpaper, we want unified wallpaper
    > Right-click On the domain, and select Create GPO in this domain and link it here
    > Go into edit mode and go to user configuration, then go under the desktop, then under desktop again
    > Click Desktop Wallpaper
        > Click Enable
        > Type the path of the file in(this should be in a shared drive for me...\\mgmt-f-group2\group2-share
        > Make sure to select fill, hit apply
    > Make sure to select the computers you want the wallpaper on the status section

![image](https://user-images.githubusercontent.com/62860262/116321719-94df8700-a788-11eb-9688-e13e2045d584.png)

    > Do a gpupdate /force

### Moves W1 and W2 user-profiles and home directories to a DFS share.
    > Firstly make sure that you have a shared drive with two folders, UserProfiles & UserFolders
    > For both folders right click --> Properties -->  Sharing Tab --> Advanced sharing and share it as UserProfiles$
        > Click Permissions and make sure the sharing permission is set as follows:
            > Everyone = Full Control
            > System = Full Control
            > Administrators = Full Control
         > Click security tab and hit advanced --> Then hit disable inheritance
             > *Remove all inherited permissions from this object*
         > Click add button --> Select a principal
             > Everyone click ok then click this folder only under applies to and show advanced permissions
             > Make sure, Traverse folder / execute file, List folder / read date, read attributes, Read Extended Attributes, Create Folders / Append date, Read Permissions
             > Hit OK
          > Click add select principal enter creator owner and give it full control
          > Click add select principal enter system and give it full control
          > Click add select principal enter Domain Admins and give it full control
    > Remeber to do this for both folders!
    > Once done continue:
    > launch group policy management 
        > Right click on your domain and choose create a new gpo in this domain and link it
        > Edit it
        > Under user configurations click polices --> Windows settings --> Folder Redirrection --> Right-click AppData(Roaming and choose properties. 
            > In the target tab choose basic - redirect everyone's folder to the same location
            > Target Folder Location choose to Create a folder for each user under the root path
            > Root Path: \\mgmt-f-group2\userFolder$
            > Click settings tab, checkmark Grant the user exclusive rights to Desktop
                > move contents of the desktop to a new location
                > Under Physical Removal, choose the Leave folder in the new location when the policy is removed
                > Click OK
                > Repeat these steps for the rest of the folders
    > Redirecting System/User Profiles
        > Open Active directory select everyone right-clicks hit properties and under profile. select profile path as \\mgmt1-f-group2\UserProfiles$\%username%

    > Mapped Drives:
        > Under User Configuration, click preferences, expand windows settings, click drive maps
        > Selection Action: Update
        > Location \\mgmt1-f-group\UserFolders$\%username% & select reconnect
