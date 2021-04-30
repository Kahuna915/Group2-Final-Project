### Configuring The Docker Service
     - Run the command "sudo apt update" to update the current packages
     - Run the command "sudo apt install apt-transport-https ca-certificates curl software-properties-common" to enable apt to use packages through HTTPS
     - Run the command "curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -" to add the GPG key for the Docker repository
     - Run the command "sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" to add the docker repository to apt resources
     - Update the current packages again
     - Check the repository you are installing from, run the command "apt-cache policy docker-ce"
     - Install docker using the command "sudo apt install docker-ce"
     - Check the status if the docker service with the command "sudo systemctl status docker"

### Adding a User to the Docker Group
     - Use the command "sudo usermod -aG docker ${_USER_}", but replace _USER_ with the username of the account you want to give access to.
     - Use the command "su - ${USER}" to apply the group membership
     - Confirm the group membership addition using the command "id -nG"
     - You can also add a user to the docker group by using the command "sudo usermod -aG docker _username_" and replacing _username_ with the username of the user you want to add to the docker group