### Creating a DFS Share
     - DFS1 and DFS2 must be added to the domain in order to complete the following steps
     - go to computer management for dfs1 and dfs2 on mgmt1
     - Under the "shares" folder create a shared folder

![](https://github.com/CameronAuler/Group2-Final-Project/blob/5d5b2ffd10d9e9a71e5a8454543e4993c0afb7da/system-configuration/mgmt2/dfs%20shares%20folder.PNG)

### using "Add Roles and Features"
     - Install DFS management tools on mgmt1
     - Add DFS namespace and DFS replication for file and storage services ong mgmt1
     - Add DFS Replication to dfs1 and dfs2
     - Go to the DFS management console on mgmt1

![](https://github.com/CameronAuler/Group2-Final-Project/blob/369c1c39869cfc76d4e854609f2a6e43666acf9f/system-configuration/mgmt2/dfs%20manange.PNG)

     - From DFS management, namespaces can be created, shares can be created and all other features of DFS can be added, changed, or deleted.