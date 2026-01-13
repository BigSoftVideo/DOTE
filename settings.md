## Settings and Transcript Options

Watch the [video tutorial](https://www.youtube.com/watch?v=udlOrRBs1z0) on YouTube.

There are two main ways to change settings for the use of _DOTE_ in general and for the current Transcript.

Note that all changes to settings and options are done immediately and cannot be undone using a shortcut or by cancelling.

### Settings

`Settings` can be opened from the `File` menu, eg. `File ➔ Settings`, or by clicking the Settings icon on the ribbon at the top right of the DOTE window.

There are several different types of settings that affect the operation of _DOTE_:

- Version control
- Editor
- Video
- Conventions
- Subtier
- Shortcuts
- External software

[![Settings](images/settings/settings.png)](images/settings/settings.png)

Some of these settings can be overridden in the current [Transcript Options](#options).
If so, then this is indicated in the `Settings`.

[![Settings](images/settings/overridden.png)](images/settings/overridden.png)

Some of the settings are only changed when the Settings dialog box is closed.

##### Version control

- [Autobackup](versioncontrol.md#autobackup) time interval default.

##### Transcript Editor

- The default [conventions](conventions.md) used for every new Transcript.
- Font size default.
- Width of name column default.
- Show or hide user-defined page-width margin.
- Show or hide mini-map.
- Auto-hide mini-map (if enabled).
- Select vertical scaling of mini-map (if enabled).
- Enable or disable highlighting of other occurrences of word/phrase.
- Enable or disable highlighting of other occurrences of selected characters.
- Enable or disable auto-completion suggestions.
- Display or ignore warnings about missing overlap endings.

##### Media Preferences

- Option to automatically restart media playback from the beginning when the end of the recording is reached.
- Option to require shift key (default) to be held when selecting a segment on the timeline.
- The default [video format](media-manager.md#add).
- The default display projection for 360 videos.
- Apply oversampling to video playback and paused video image display.

##### Mondadaian action alignment symbols

- The default [subtier alignment symbols](tiers.md#assign) can be defined and ordered by the user.
The default list includes some of the most commonly used symbols in the Mondadaian system.
Note that this list can be rearranged by selecting, dragging and dropping an item in the list.

##### Additional audio and video decoding

- Install or config FFmpeg manually if necessary.

##### Application error reporting

- Select the most appropriate error reporting mode.

##### Shortcuts

- A number of common [shortcuts](commands.md) can be redefined by the user.

##### Custom media controls

- The user can redefine the jump intervals for short jump forward/back and long jump forward/back.
The defaults are 1 second for the short jump and 4 seconds for the long.
The jumps can be activated using the [playback buttons or the playback shortcuts](play.md).
- Additionally, the user can define a universal frame rate (fps) that determines what happens when using the one frame forward/back buttons or shortcuts.
The default is 30fps.
If the video being played is encoded with a different frame rate than in Settings, then frame forward/back may either jump more than one frame or no frame occasionally.

##### Other settings

- Number of recent transcripts to list in Project Manager.
- Option to disable clicking outside of dialog box to cancel.
- Option to disable animated reminder to turn on follow video-cues in specific circumstances.

[![Transcript Options](images/settings/ffmpeg-installed.png)](images/settings/ffmpeg-installed.png)

### Transcript Options <a id='options'></a>

`Transcript Options` can be opened from the `Project` menu, eg. `Project ➔ Transcript Options`, or by clicking the `Options ⚙` button at the top left of the [Transcript Editor](editor.md).

[![Transcript Options](images/settings/options.png)](images/settings/options.png)

The path to the Project folder on your computer's file system is displayed and can be opened by clicking the button `Open Directory`.

There are several different types of options that affect how the Editor works.
Some of these are inherited from `Settings` and can be overridden on a transcript by transcript basis.
They can be "reset" to the Default if they vary from that in `Settings`.

[![Transcript Options](images/settings/overridden2.png)](images/settings/overridden2.png)

#### Override settings in this transcript only

Many of these options are only changed when the Transcript Options dialog box is closed.

Click the button and the folder will be opened in your file browser.
- Font size for the current Transcript in the [Editor](ui.md).
- Width of name column for the current Transcript.
- Display page-width margin for the current Transcript.
- Display or ignore warnings about missing overlap endings.
- The [conventions](conventions.md) used for this Transcript.

#### Transcript automation

There are Transcrip settings to automate the auto-completion and recognition of subtiers.

- The [translation and gloss subtiers](tiers.md) for this Transcript.
One or more than one of each can be added.
If such a subtier is added, then it will also be autocompleted after typing and autocompleting a new speaker in the Transcript Editor.
- The [named subtier types](tiers.md) for this Transcript.
Note that this list can be rearranged by selecting, dragging and dropping an item in the list.
It is up to the user to indicate whether or not each subtier will also be autocompleted after typing and autocompleting a new speaker in the Transcript Editor.

Note: Because some options are tracked by _DOTE_, they may be reset to a prior state if the user resets to an earlier Checkpoint or Autobackup.
For example, [named subtier types](tiers.md) may be altered because they were in a different state in an earlier version of the Transcript.
This is necessary because they need to match the prior state of the Transcript and its subtiers in order to preserve history.
