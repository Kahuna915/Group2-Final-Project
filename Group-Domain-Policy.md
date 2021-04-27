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
    > Do a gpupdate /force

### Moves W1 and W2 user-profiles and home directories to a DFS share.
    > 
