Connecting Ubuntu (WSL2) Unix with AWS EC2 using visual studio code
Step 1: Install the Extension
Go to code.visualstudio.com.
Download: Click the big button that says "Download for Windows."
Install: Run the .exe file you just downloaded.
Pro-tip: During installation, check the boxes that say "Add 'Open with Code' to Windows Explorer context menu." This allows you to right-click any folder and open it instantly.
Open Visual Studio Code on Windows.
Click the Extensions icon on the left sidebar (or press Ctrl + Shift + X).
Search for "Remote - SSH" (published by Microsoft) and click Install.
Step 2: Configure the Connection
Press Ctrl + Shift + P to open the Command Palette.
Type "Remote-SSH: Open SSH Configuration File..." and select it.
Choose the first file path (usually C:\Users\Binod Gyawali\.ssh\config).
Paste the following block into the file (replacing the placeholders):
Plaintext
Host abcd-ec2 (replace abcd with yours)
    HostName 3.xx.xxx.xxx (Your EC2 Public IPv4 Address)
    User ec2-user (or ubuntu)
    IdentityFile "C:/Users/Binod Gyawali\Downloads\your-key.pem" (the Windows path to your .pem file).
Save the file (Ctrl + S).
Step 3: Connect to EC2
Click the green icon in the very bottom-left corner of VS Code (it looks like ><).
Select Connect to Host... from the menu that pops up.
Select your nickname (abcd-ec2).
A new VS Code window will open. If prompted, select Linux as the platform and click Continue for the fingerprint warning.
## You are now "inside" the EC2! 
A menu will pop up at the top of your VS Code window.
Select "Connect to Host..." from that menu.
You should see your nickname binod (if you saved the config file earlier).
Click it.
VS code is ready to use. Make sure your EC2 instance is in running mode

