Connecting Unix in macOS with AWS EC2 instance

Step 1: Move your Private Key (.pem file) to your Mac
If you are using the same AWS Key Pair as your Windows machine, you need that .pem file on your Mac.
Transfer the file: Move the .pem file from your Windows computer to your MacBook (via USB, AirDrop, or a secure cloud drive).

Step 2: Store it safely: Open your Terminal and move the key to the standard SSH folder:
Bash
mkdir -p ~/.ssh
mv ~/Downloads/MY-key.pem ~/.ssh/

Step 3: Fix Permissions: macOS is very strict. If your key is "too open," SSH will reject it. Run:
Bash
chmod 400 ~/.ssh/MY-key.pem

Step 4: Download and Install VS Code
Open Safari (or any browser) and go to: https://code.visualstudio.com/download
Click the Mac button to download the .zip file.
Go to your Downloads folder in Finder.
Double-click the VSCode-darwin-universal.zip file. This will extract an application named "Visual Studio Code."
Important: Drag the "Visual Studio Code" icon into your Applications folder. If you don't do this, the app won't update correctly.

Step 5: Install the Remote - SSH Extension
Open VS Code on your MacBook.
Click on the Extensions icon on the left sidebar (or press Cmd + Shift + X).
Search for "Remote - SSH" by Microsoft and install it.

Step 6: Configure the SSH Connection
Press Cmd + Shift + P to open the Command Palette.
Type "Remote-SSH: Open SSH Configuration File..." and select it.
Choose the file path: /Users/Binod/.ssh/config.
Add the following block to the file (replace placeholders with your actual info):
Plaintext
Host zynt-ec2
    HostName 3x.xxx.xxx.xxx  # Your EC2 Public IP or DNS
    User ec2-user           # Or 'ubuntu' depending on your AMI
    IdentityFile ~/.ssh/BGKey1.pem

Note: For Amazon Linux, the user is usually ec2-user. For Ubuntu, it is ubuntu.

Step 7: Connect to EC2
Click the blue icon (looks like ><) in the very bottom-left corner of VS Code.
Select Connect to Host... from the menu.
Click on my-ec2-instance (the name you gave it in the config).
A new VS Code window will open. If prompted, select Linux as the platform and click Continue.

## Connection of vs code in macOS with AWS EC2 instance is successful
