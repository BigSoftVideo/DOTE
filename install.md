## How to download and install _DOTE_

_DOTE_ is a desktop application that runs on your local computer.
It is very easy to download and install the software and run it on the Windows and Mac desktop platforms.
It should run on the latest versions of Microsoft Windows 10 or 11 and also Apple macOS (10.10 Yosemite or later; also macOS 12 for the newer Apple Silicon M-series).
Let us know if you have a problem installing and running _DOTE_ on these platforms.
Theoretically, it should also run on Linux, but we don't support this.
Contact us if you are interested in using _DOTE_ on this platform.
Note that only one instance of _DOTE_ is allowed to run at the same time.

Choose the correct and latest version for your operating system from our [_DOTE_ Webshop](https://www.dote.aau.dk/downloads) or you can browse archived [releases](https://github.com/BigSoftVideo/DOTE/releases) on our public _DOTE_ GitHib repository.

- **Windows**
    - To install the Windows version, `double click` on the `EXE` file.
    - If you get a Windows warning message, then click the `More info` link, and choose `RUN ANYWAY`.
    - _DOTE_ will start after the install is complete.
    - The _DOTE_ icon should also appear on your desktop.
    In future, just `double click` the icon and _DOTE_ will start.

[![Windows warning](images/install/Win-defender.png)](images/install/Win-defender.png)

[![Windows run anyway](images/install/Win-defender-run.png)](images/install/Win-defender-run.png)

- **macOS**
    - For macOS, double click on the _DOTE_ icon (`DMG`).
    - Drag and drop the unpacked `DOTE` app into your `Applications` folder and `double click` to run.
    - NOTE: your macOS system settings may be set to restrict installations.
    - In that case, open `System Preferences`, select `Security & Privacy`, select `General` tab, and select and approve `Allow apps downloaded from`App Store and identified developers`.
    You may need to _unlock_ your settings to make these changes.

[![macOS install](images/install/dmg.png)](images/install/dmg.png)

### End User License Agreement

The first thing you need to do after installing _DOTE_ is agree to the Terms and Conditions of the EULA.

[![EULA](images/install/eula.png)](images/install/eula.png)

If you do, then _DOTE_ won't ask again on that machine.
If you don't, then _DOTE_ will not start.

### Installation problems <a id='problems'></a>

On Windows, the installation may fail because Windows Defender does not recognise the software.
You can set Defender to allow _DOTE_ to run on your computer.

On Windows, the installation may fail because your Windows setting does not allow software to be installed except from the App Store.
If you wish to install _DOTE_, then you have to change that setting to allow apps to be installed from 3rd party sources.

Another reason for failure is that you may have an Anti-virus/malware programme installed.
It may not recognise _DOTE_ and warn you about installing/running the software on your computer.
Just set the Anti-virus software to trust _DOTE_.

If the installation fails because you do not have administrator rights, then you may need to get permission from your IT support to allow installation of the _DOTE_ software.

- For example, you may not have permission in Windows (Group Policy) to install unknown or unapproved software.
This is a local problem with how your computer has been setup by a security conscious IT support.
    - Ask your system administrator to allow running `DOTE_ExecutionStub.exe` AND `DOTE.exe`.
    The installer must be run after this has succeeded, then you should be able to run _DOTE_ normally.
    - Alternatively use _DOTE_ on a computer that is not constrained by such policies (for example a computer that you own personally).

### Installing other open source packages that _DOTE_ needs for specific purposes

#### Installing Git <a id='git'></a>

To use Checkpoints and to view Autobackups, you will need to install the free open-source software called _Git_ on your computer. See [Checkpoints](versioncontrol.md#setup).

#### Installing FFmpeg <a id='ffmpeg'></a>

_DOTE_ can import many audio formats on its own in order to generate a waveform automatically, but not all.
If you have trouble generating a waveform for a video or audio clip, then one can either transcode the clip (see [Tips](tips.md)) and try again by importing the new video or by regenerating the waveform (see [Media Manager](media.md)).

Alternatively, you can let _DOTE_ install the free, open source _FFmpeg_ on your computer and add the folder path to `ffmpeg.exe` to your _DOTE_ [Settings](settings.md).

1. Go to Settings and scroll down to the bottom to see the `Additional Audio & Video Format Support` section.
2. Reset the file path (if it is blank or has an incorrect file path).
3. Select `Download FFmpeg and FFprobe`.
4. The files will be downloaded and installed.
5. The "Not found" indicators should change to "Available".
6. Try restarting _DOTE_ if something looks amiss.

BEFORE:

[![FFmpeg missing](images/settings/ffmpeg-missing.png)](images/settings/ffmpeg-missing.png)

AFTER:

[![FFmpeg installed](images/settings/ffmpeg-installed.png)](images/settings/ffmpeg-installed.png)

Like many other software, _DOTE_ has to do this extra step because of licensing restrictions.

NOTE: After using _DOTE_ to install _FFmpeg_, if you reinstall _DOTE_ or update to a newer version, then _FFmpeg_ will be reinstalled automatically.

##### Installing FFmpeg yourself

Both _ffmpeg_ and _ffprobe_ have to be installed.
See [these instructions](https://bbc.github.io/bbcat-orchestration-docs/installation-mac-manual/) for more detail if you get stuck.

1. Manually set the file path to the folder in which you installed the `ffmpeg.exe` and `ffprobe.exe` files (in the same folder).
2. The "Not found" indicators should change to "Available".
3. Try restarting _DOTE_ if something looks amiss.

For a [Windows](https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip) installation, the folder path might look like this, depending on how you installed it:
- `C:\FFmpeg\bin\`
- `C:\Program Files\FFmpeg\bin`

For a [macOS](https://evermeet.cx/ffmpeg/) installation, the folder path might look like this, depending on how you installed it:

- `/usr/local/bin`
- `/opt/homebrew/bin`

You may have to request permission from your IT services to install these software.
And you may have to unlock a folder (on macOS) to be able to install into that folder.
Finally, you may not have access rights to the standard folder for installation (on macOS), so select a public folder that you do have access to.

### _DOTE Pro_ license key

You will need to purchase and enter a [license key](pro.md#license) to unlock the premium features in _DOTE Pro_.

### Updating to a new release

When you rung _DOTE_, it will remind you if there is a new release available online.
It is up to you to manually download the new release and install it.

To update _DOTE_ on both operating systems, just close _DOTE_, download the update and follow the same procedure above.
_DOTE_ will be updated and restart automatically.
