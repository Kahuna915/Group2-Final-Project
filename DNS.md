### DNS Configuration
     - Exit Active directory and go to DNS in server manager
     - Right click on Dc01 or Dc02 and select DNS manager
     - Go down to Reverse zone lookup
     - Here right click on it and add a reverse zone for 172.16.1
     - After this go up to Forward lookup zones group2-final.local
     - In here right click and hit add New AAA host
     - Type in all the Ip addresses and names assigned to you