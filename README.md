# LHP2-Archipelago-Android-Setup
If any help is needed for the setup, make sure to contact Rainbow (notrainbowsteve) in the [Discord](https://discord.gg/8Z65BR2).

## Required Hardware
- A computer/laptop that can run Windows (with Windows installed)
- A phone/tablet that can run Android (with Android installed)
## Required Software
- GameNative [Link](https://github.com/utkarshdalal/GameNative)
- Reloaded II Mod Loader [Link](https://reloaded-project.github.io/Reloaded-II/QuickStart/)
  -  Requires .NET 9.0 or higher [Link](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)
  -  Requires Visual C++ Runtime [Link](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-supported-redistributable-version)
- The Lego Harry Potter 5-7 Archipelago Mod [Link](https://github.com/jradcode23/LHP2-Mod/releases)
- Google Drive (or some other way to transfer files from your Windows computer to your Android phone, like a USB drive)
- Geekbench 6 for Android [Link](https://play.google.com/store/apps/details?id=com.primatelabs.geekbench6&hl=en_US)
## Optional Software
- Some sort of Android file manager
  - Here is the one I used [Link](https://play.google.com/store/apps/details?id=com.ace.ex.file.manager&hl=en_US)
- A text file editor on your Android phone
  - Here is the one I used [Link](https://play.google.com/store/apps/details?id=com.maxistar.textpad&utm_source=na_Med)
## First Time Setup File Setuo
- Follow the Steam instructions of the [First Time Setup guide](https://github.com/jradcode23/LHP2-APWorld/blob/main/worlds/lhp2/docs/setup_en.md#first-time-setup) for the game on a device running Windows. Most of these files downloaded and generated you will be needing to transfer over to your Android phone.
- Here is a list of all of the files you need to transfer over to your Android phone from your Windows computer, and where they are located:
  - Your whole Reloaded-II folder
     - Located at wherever you chose to install Reloaded-II
  - dinput8.dll and Reloaded.Mod.Loader.Bootstrapper.asi
     - Located in your Lego Harry Potter Years 5-7 game folder
  - ReloadedII.json
    - Located at C:\Users\[USER]\AppData\Roaming\Reloaded-Mod-Loader-II (replace [USER] with your Windows profile name)
- Here is a list of all the files you need to download to your Android phone:
  - .NET 9.0 or higher
  - Visual C++ Runtime
  - GameNative
## First Time Setup Installation Instructions
- Once you download the [latest release APK](https://github.com/utkarshdalal/GameNative/releases), run the APK file, and install it to your phone
- Open up the GameNative app, and sign into your Steam or GOG account
- Download and install Lego Harry Potter Years 5-7 onto your phone through GameNative
- Launch your game, and make sure it runs. This could take up to 10 minutes the first time, depending on how slow your phone is, however it wil usually only take a few minutes
- Make sure every file/folder that you need on your phone is either downloaded onto or transferred over to your phone's Downloads folder
  - This is important, because GameNative has access to it, and we will be abusing that)
- Tap on your game in GameNative, but do not launch it
- Select the settings button for the game
- Tap "Open Container"
  - This opens up the desktop environment on your Android phone, so that you can move files around within the virtual and real drives
- Once the file explorer loads, open up the D:\ drive to access your Android Downloads folder
- Move dinput8.dll and Reloaded.Mod.Loader.Bootstrapper.asi into your game folder
  - Your game folder is located at the default Steam installaton in the virtual C:\ drive, but it can also be found in the virtual A:\ drive (it does not matter which one you do, they share files)
  - You can also find your game files path in the menu screen for the game on GameNative if you wish to do this step from within the Android file manager of your choice
- Move your whole Reloaded-II folder to any path on your C:\ drive, however I reccomend putting it into the Downloads folder for the virtual C:\ drive, which is located at C:\Users\xuser\Downloads
- In a file editor, you will need to edit the file paths in the ReloadedII.json file
  -This can be done either inside of the dekstop environment, or in a text editor downloded to your Android phone (or from your Windows computer if you have not transferred the file over yet)
  - The file paths need to follow the virtual C:\ drive's path to whereever you put the Realoded-II folder (only edit the parts of the file structure before the foler itself)
-Take the edited Reloaded-II.json file, and place it in the virtual C:\ drive at the path C:\Users\xuser\AppData\Roaming\Reloaded-Mod-Loader-II
  - You will likely have to create the Reloaded-Mod-Loader-II folder yourself, because that is not naturally there on the virtual drive
- Leave the desktop environment, and go to your settings for the game in GameNative
- Tap on "Edit container"
- Scroll down, and toggle on the "Unpack Files"
- Leave the settings and start the game up normally (through the  play button)
  - Your game will crash, however this is supposed to happen, because the only reason we are launching it is to generate a file that we need to be able to launch the game correctly
- Go back into the desktop envirnoment, and go into your game folder
- Rename your "harry.exe" file anything else (it literally does not matter)
- Rename the newly generated file called "harry.exe.unpacked.exe" to "harry.exe"
- Leave the desktop environment, and go to your settings for the game in GameNative, and tap on "Edit Container Again"
- Scroll down and toggle off the "Unpack Files" option
- Go to the "Advanced" tab at the top, and change the Startup Selection from "Essential" to "Normal"
- Go to the "Environment" tab at the top, and scroll all the way down
- Tap on the little circle with a + symbol in it to create a new environment variable
  - In the "Name" text box, type "WINEDLLOVERRIDES"
  - In the "value" text box, type "dinput8=n,b"
- Go to the "Controller" tab at the top, and toggle on "Use Steam Input"
- Go to the "Emulation" tab at the top, and change the Box64 Preset to "Unity Mono Bleeding Edge"
- Download Geekbench 6, and open it up
- Tap the GPU tab, and look at what GPU you have, and keep note of it for later

These next few steps are specific to Adreno GPU's however it will be updated to show more GPU configurations as more people get support and report what configs they use
- Go to the "Graphics" tap at the top, and change these settings to configure to your GPU:
#### Adreno GPU Configuration
- Set your Graphics Driver to option "Turnip (Adreno)"
- Set your Graphics Driver Version to "25.1.0"
- Set the DX Wrapper option to "WineD3D"
- Set the DXVK Version to "2.6-arm64ec"
