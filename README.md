# USB File Encryptor
## Summary
This script uses an external USB that holds a cryptography library fernet key that the computer uses to En- and De-crypt a user chosen directory. This means the chosen directory, I like to call it vault, can not be accessed without the external USB or key. 
## Requirements
**[Python 3.12.5](https://www.python.org/downloads/release/python-3125/) or newer
<br />
[PIP](https://pip.pypa.io/en/stable/installation/)**
<br />
Any Python code editor such as [VS code](https://code.visualstudio.com/download)
## How to set up
Copy this repository:
```
git clone https://github.com/EggDogue/USB-En-and-Decryptor.git
cd USB-En-and-Decryptor
```
Install the [cryptography](https://pypi.org/project/cryptography/) library:
```
pip install cryptography
```
If you want to later convert this to an executable file:
```
pip install pyinstaller 
```
Create the key:
```
cd scripts
py Key_Creator.py
```
And copy it into a txt file on your USB, which should look like this:
```
ACdIRIb_fpeSiSs189H3R7BPoYkOpT6UcvDL_olsW_Q=
```
__Do not use this key, it is only for showing what the file should look like! Use the generated key or a custom key you create!__
<br />
<br />
<br />
Then open the USB_En_and_Decryptor.py and Initial_Encryptor.py and change the fist lines in both files to the directories you want:
```
code Inital_Encryptor.py
code USB_En_and_Decryptor.py
```
 change in both:
```
 key = #path to key on USB example: r'D:\key.txt'
 directory = #path to vault directory example: r'C:\Users\local\Documents\vault'
```
Run the initial encryptor to finish the setup:
```
py Inital_Encryptor.py
```
```
py USB_En_and_Decryptor.py
```
Now you can always decrypt your vault from here by running the above command or you make your life easy by converting it into an executable by running:
```
pyinstaller --onefile --windowed USB_En_and_Decryptor.py
```
Now wait until the process has finished and type:
```
cd dist
explorer .
```
Now you can copy and paste this executable onto your desktop or paste it into your autostart through:
```
cd C:\Users\<YourUsername>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
explorer .
```
