# Mounting a Remote SMB Share on Ubuntu 22 by Prime Murcia

## Installation

1. **Install cifs-utils:**

    ```bash
    sudo apt-get install cifs-utils
    ```

2. **Create SMB Credentials File:**

    Open the file for storing SMB credentials:

    ```bash
    sudo nano /etc/smbcredentials
    ```

    Add your SMB username and password:

    ```plaintext
    username=your_username
    password=your_password
    ```

3. **Secure SMB Credentials File:**

    Set proper permissions on the smbcredentials file:

    ```bash
    sudo chmod 600 /etc/smbcredentials
    ```

4. **Edit /etc/fstab:**

    Open the /etc/fstab file for editing:

    ```bash
    sudo nano /etc/fstab
    ```

    Add the following line to mount the SMB share:

    ```plaintext
    //youripaddress/foldername /pathfiles/foldername cifs credentials=/etc/smbcredentials,uid=user,gid=user,vers=3.0 0 0
    ```

    Replace the placeholders with your specific information.

5. **Mount the SMB Share:**

    Apply the changes made in /etc/fstab:

    ```bash
    sudo mount -a
    ```

    The SMB share should now be mounted at the specified local path.

    **Note:** If there are no errors, the mount command will not produce any output.

## Additional Notes

- Ensure the SMB server allows access from your IP address.
- Adjust firewall settings if necessary.
- Review cifs-utils and SMB documentation for additional configuration options.

This guide provides a basic setup for mounting an SMB share on Ubuntu. Adjustments may be needed based on your specific environment and requirements.
