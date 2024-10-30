_Secure Shell (SSH) is a protocol used to securely log into remote systems. SSH uses encryption to protect the 
communication between the client and server. This guide will walk you through setting up an SSH server, generating 
SSH keys, and configuring key-based authentication._

### 1. Install the SSH Server
    
- On Ubuntu/Debian: `sudo apt update`, `sudo apt install openssh-server`
- On CentOS/RHEL: `sudo yum install openssh-server`
- On Fedora: `'sudo dnf install openssh-server'`

### 2. Start and Enable the SSH Service
1. Start the SSH service: `sudo systemctl start ssh`
2. Enable the SSH service to start on boot: `sudo systemctl enable ssh`

### 3. Configure SSH Server Settings
1. The SSH server configuration file is located at /etc/ssh/sshd_config. You can modify it using a text editor like  
   nano or vim: `sudo nano /etc/ssh/sshd_config`
2. Common configuration options:
   - Change the default SSH port: `Port 2222` - Replace 2222 with your desired port number.)
   - Disable root login (recommended for security): `PermitRootLogin no`
   - Allow only key-based authentication (disabling password authentication): `PasswordAuthentication no`
   - Restrict access to specific users: `AllowUsers username`

### 4. Restart the SSH Service
After making changes to the configuration file, restart the SSH service to apply them:

`sudo systemctl restart ssh`

### 5. Generate an SSH Key Pair
1. On your local machine, generate a new SSH key pair using the ssh-keygen command:

    `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` where:
    - `-t rsa` specifies the type of key to create (RSA is the most common)
    - `-b 4096` sets the number of bits in the key to 4096 (a larger number means more security)
    - `-C "your_email@example.com"` is a comment to label the key (optional, often used to identify the key).
2. Follow the prompts:
    - You will be asked to specify a location to save the key (default is `~/.ssh/id_rsa`)
    - You can also set a passphrase for an additional layer of security, but this is optional

### 6. Copy the Public Key to the SSH Server
1. The public key must be copied to the SSH server to allow key-based authentication.
2. Using ssh-copy-id (recommended method): `ssh-copy-id username@server_ip` where:

    - Replace `username` with your SSH username and `server_ip` with the IP address of your server
    - The public key (`~/.ssh/id_rsa.pub`) will be copied to the server and appended to the `~/.ssh/authorized_keys` 
      file.
3. Manual method:
    - Copy the public key to the server: `scp ~/.ssh/id_rsa.pub username@server_ip:/home/username/`
    - Log in to the server: `ssh username@server_ip`
    - Append the public key to the `~/.ssh/authorized_keys` file:
        

        mkdir -p ~/.ssh
        cat ~/id_rsa.pub >> ~/.ssh/authorized_keys
        chmod 600 ~/.ssh/authorized_keys
        rm ~/id_rsa.pub

### 7.  Log in with SSH
1. Once your key is copied to the server, you can log in using: `ssh username@server_ip` (SSH will automatically use 
 your private key (`~/.ssh/id_rsa`) to authenticate)
2. If you configured SSH to use a different (non-default) port (e.g., 2222), specify it when logging in:
`ssh -p 2222 username@server_ip`
3. To further secure your server, you can disable password authentication entirely, ensuring that only users with 
the correct SSH keys can log in. Edit the `/etc/ssh/sshd_config` file and set: `PasswordAuthentication no`. Restart 
   the SSH service with `sudo systemctl restart ssh`.


### 8. Additional Security Measures
1. **Set Up SSH Key Passphrase.**  If you didn’t set a passphrase when generating your SSH keys, you can add one 
   later: `ssh-keygen -p`. This will prompt you to enter and confirm a passphrase. 
2. **Use SSH Agent for Passphrase Management.** SSH Agent can cache your passphrase so you don't need to enter it 
   every time: 
   - Start the SSH agent in the background: `eval "$(ssh-agent -s)"`
   - Add your SSH private key to the agent: `ssh-add ~/.ssh/id_rsa`
3. **Set Up Two-Factor Authentication (2FA).** You can add an extra layer of security by setting up two-factor 
   authentication using tools like Google Authenticator.


### 9. Troubleshooting SSH
1. Permission Denied? Ensure that the `~/.ssh` directory and the authorized_keys file on the server have the correct 
   permissions:
      
         chmod 700 ~/.ssh
         chmod 600 ~/.ssh/authorized_keys

2. Connection Refused? Make sure the SSH service is running on the server: `sudo systemctl status ssh`
3. Cannot Connect to Server on a Different Port? Ensure that the server's firewall allows traffic on the custom SSH 
   port: 

   `sudo ufw allow 2222/tcp`
