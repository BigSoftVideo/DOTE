## How to download and install _DOTE_

_DOTE_ is a desktop application that runs on your local computer.
It is quite easy to download a release build and run it on the Windows and Mac desktop platforms.
It should run on the latest versions of Microsoft Windows 10 or 11 and also Apple macOS (10.10 Yosemite or later; also macOS 12 for the newer Apple Silicon M-series).
Let us know if you have a problem installing and running _DOTE_ on these platforms.
Theoretically, it should also run on Linux, but we don't support this.
Contact us if you are interested in using _DOTE_ on this platform.

- Choose the correct and latest version for your operating system from the [RELEASES](https://github.com/BigSoftVideoDOTE-beta-testing/releases) page of our GitHib repository.

    - **Windows**
        - To install the Windows version, `double click` on the `EXE` file.
        - If you get a Windows warning message, then click the `More info` link, and choose `RUN ANYWAY`.
        - _DOTE_ will start after the install is complete.
        - The _DOTE_ icon should also appear on your desktop.
        In future, just `double click` the icon and _DOTE_ will start.

    - **macOS**
        - For macOS, double click on the _DOTE_ icon (`DMG`).
        - Drag and drop the unpacked `DOTE` app into your `Applications` folder and `double click` to run.
        - NOTE: your macOS system settings may be set to restrict installations.
        - In that case, open `System Preferences`, select `Security & Privacy`, select `General` tab, and select and approve `Allow apps downloaded from`/`App Store and identified developers`.
        You may need to _unlock_ your settings to make these changes.

### Installation problems <a id='problems'></a>

If the installation fails, then you may need to get permission from your IT support to allow installation of the _DOTE_ software.

- For example, you may not have permission in Windows (Group Policy) to install unknown or unapproved software.
This is a local problem with how your computer has been setup by a security conscious IT support.
    - Ask your system administrator to allow running `DOTE_ExecutionStub.exe` AND `DOTE.exe`.
    The installer must be run after this has succeeded, then you should be able to run _DOTE_ normally.
    - Alternatively use _DOTE_ on a computer that is not constrained by such policies (for example a computer that you own personally).

### Installing other open source packages that _DOTE_ needs for specific purposes

#### Installing Git <a id='git'></a>

To use Checkpoints and view Autosaves, you will need to install the free open-source software called _Git_ on your computer. See [Checkpoints](versioncontrol.md).

#### Installing FFmpeg <a id='ffmpeg'></a>

DOTE can import many audio formats on its own in order to generate a waveform automatically, but not all.
If you have trouble generating a waveform for a video or audio clip, then one can either transcode the clip (see [Tips](tips.md)) and try again by importing the video or by regenerating the waveform (see [Media Manager](media.md)).
Alternatively, you can install the free, open source _FFmpeg_ ([Windows](https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip) or [macOS](https://evermeet.cx/ffmpeg/)) on your computer and add the folder path to `ffmpeg.exe` to your _DOTE_ [Settings](settings.md).

### Serial key

- You will need a serial key to continue using the beta version of _DOTE_.
Just enter the serial key once and _DOTE_ won't ask again.

### Updating to a new release

- To update _DOTE_ on both operating systems, just follow the same procedure above and _DOTE_ will be updated and start automatically.