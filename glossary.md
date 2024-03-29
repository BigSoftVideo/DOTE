## Glossary of key terms in _DOTE_

Below is a list of key terms in alphabetical order with short definitions and links to relevant help pages for more information.

### 2D Video <a id='2D'></a>

In _DOTE_ terminology, we use 2D Video to refer to the traditional recordings made by video cameras that flatten and render the visible 3D world onto a rectangular frame of digital pixels.
The use of the nomenclature of dimension and angle (Eg. 2D, 2½D, 3D, 180, 360) is becoming standardised in more technical research on advanced recording and immersive technologies.

See also [360-degree Video](#360).

### 360-degree Video <a id='360'></a>

A 360-degree Video recording is made using a special 360-degree camera with at least two wide-angle lenses arranged in a fixed configuration around a central axis.
Using special algorithms, a spherical view of everything visible (panorama) around the fixed point of the camera can be reconstructed using a [Projection](#projection) mapping.
Such video recordings are passive in that the [Viewport](#viewport) can be rendered in a digital media player or in Virtual Reality from only that fixed point.
Some 360-degree cameras can also recover depth mapping and render a stereoscopic view in all directions.
180-degree videos represent the visible field in a half-sphere.
_DOTE_ does not support 180-degree videos directly, but if they are transposed into an equirectangular format with the other half of the sphere behind the camera rendered black, then they can be imported.

See [Equirectangular](#equi) and [Spatial Audio](#spatial-audio).

### Active Media <a id='active'></a>

When media files are added to a Project using the [Media Manager](media.md) they can be activated to appear in the current Transcript.
If a media file is deactivated, it will not be available for use in the current Transcript.

### Alignment Symbol <a id='align-symbol'></a>

An alignment symbol (Mondadian conventions) is a unique symbol reserved for use in a transcript to indicate the temporal alignment of an action in a [Subtier](#tier.md) with the [HEAD](#head) of the [Neighbourhood](#neighbourhood).

See [Realignment](#align).

### Ambisonic <a id='ambisonic'></a>

An Ambisonic audio recording is a representation of the [Spatial Audio](#spatial-audio) field around a fixed point.
Special Ambisonic microphones with at least four microphone capsules in a fixed configuration can be used to capture multiple channels of sound that later can be rendered through headphones to reconstruct the Spatial Audio field from the 'point of view' of the hearer.
In later releases, _DOTE_ will support Ambisonic recordings in a standard format and render the Spatial Audio field to match the [360-degree Video](#360) recording with which it is associated.

### Autocompletion <a id='autocomplete'></a>

Autocompletion is the automatic, context-sensitive prompting of possible character or symbol strings that the user can select from.
There are several aspects of a Transcript that can be [Autocompleted](transcript.md#autocomplete) in the [Editor](transcript.md).
1. The initial [Speaker-id](#id) column.
1. Named [Subtier Types](#subtier): action, translation and gloss.
1. Special symbols and symbol pairs.
1. [Overlaps](#overlap).

### Autobackup <a id='autobackup'></a>

DOTE provides a behind-the-scenes automatic backup system called [Autobackup](versioncontrol.md#autobackup).
After a user-defined time interval ([Settings](settings.md)), a new snapshot is taken of the current Transcript if there are unsaved changes.
The Transcript itself is not saved to disk; only a backup copy is made.

### Checkpoint <a id='checkpoint'></a>

A [Checkpoint](versioncontrol.md#checkpoint) is a user-initiated snapshot of the current Transcript if there have been changes made since the last known Checkpoint, regardless of whether or not the Transcript has been saved.
A message can be added to each Checkpoint to log the history of changes in a storied fashion.
Messages are usually in the active, imperative voice describing the changes made by the new Checkpoint since the last one, eg. "Edit lines 45-47: add stress and loudness."

### Comment <a id='comment'></a>

A comment is a message in a Transcript by a transcriber that concisely describes something happening in the data that cannot be easily represented using the traditional conventions, eg. in the [Jeffersonian conventions](jefferson.md) comments are written within double parentheses: `((comment))`.

Cf. [Technical Comment](#tech-comment)

### Conventions <a id='conventions'></a>

In qualitative research, events in social interaction can be described in textual form using a variety of Conventions to carefully document specific phenomena concerning speech and action.
_DOTE_ has been implemented to adhere as closely as possible to two standardised transcription Conventions, eg. [Jeffersonian](jefferson.md) and [Mondadaian](mondada.md).

### CS Mode <a id='cs-mode'></a>

When a media [Activated](#active) in a Transcript is played back, there is a toggle option in the [Editor panel](transcript.md) called [CS Mode](sync-code.md#cs-mode) that synchronises playback with the relevant lines of the Transcript that match the timecode segment on the [Timeline](timeline.md).
In _DOTE_, this is only possible if [Sync-codes](sync-code.md) have been manually added to the Transcript.

See also [Synchronised Media](#sync).

### Editor <a id='editor'></a>

The Editor is the [Panel](ui.md) in which the text of the Transcript is created and edited.

### Equirectangular <a id='equi'></a>

An Equirectangular video describes one method for squeezing a [360-degree Video](#360) panoramic recording into a standard 2D rectangular video frame.
Unavoidably, it is massively distorted and thus difficult to 'read' in terms of the relative positioning of people/objects and of the directionality of actions and gaze, eg. who is looking at whom.
It is also a term for one of the [Projections](#projection) that can be rendered from the recording format into a [Viewport](#viewport).

### Git <a id='git'></a>

[Git](https://git-scm.com) is a free, open source distributed version control system used by _DOTE_.

See [Version Control](#version) and [Checkpoint](#checkpoint).

### HEAD <a id='head'></a>

The HEAD of a [Neighbourhood](#neighbourhood) is always the first line.
It is either a primary speaker line or a [Timing Interval](#interval) line, and it provides the a notional temporal structure to which other lines in the [Neighbourhood](#neighbourhood) adhere.

### Jump Cut <a id='jump-cut'></a>

[Video-cues](cues.md) can initiate a transition between one view of the video and another that is displayed in the [Viewport](#viewport) of a [Video Panel](#video).
This transition can be sudden -- a Jump Cut -- or [Smooth](#smooth).

Cf. [Zoom](#zoom) and [Pan](#pan).

### Line number <a id='line-number'></a>

There are two senses of Line Number in DOTE:

1. The abstract Line Numbers in the Editor.
The Transcript Editor assigns a temporary, unique number in ascending order to each and every line.
1. The Line Numbers assigned when the Transcript is [Exported to an RTF document](export.md).
The Exporter can assign a permanent, unique line number in ascending order to every line or some of the lines according to a principle, such as only assign a Line Number to a line if it has a [Speaker-id](#id), a [Timing Interval](#interval) and/or a [Comment](#comment).
Thus, these two senses are not equivalent.

### Loop <a id='loop'></a>

Media can be looped by selecting a portion of the [Waveform](#waveform) on the [Timeline](timeline.md#loop).
During playback, this selected section will [Play](play.md) repeatedly.

### Media Manager <a id='media'></a>

The [Media Manager](media.md) is a tool to add media files to an individual [Project](project.md).
It is used to import (by copying), configure and delete media files, as well as make them [Active](#active) in the current Transcript.
A Project can contain multiple media files, and each Transcript in a Project can activate one or more of these media to use in the [Timeline](timeline.md) and [Video Panel(s)](video.md).

### Neighbourhood <a id='neighbourhood'></a>

A [Neighbourhood](tiers.md) is a concept we developed to better encapsulate what goes on during a recording in which a relatively short, fixed time period elapses.
Sets of lines in a transcript can be grouped together temporally because they try to represent events that happen within a single, continuous duration in time.
In practice, the duration of time is most often dictated by the maximum number of characters (with a specific font size) that are available on a single line on a standard page of text, eg. A4/Letter.
A new Neighourhood begins when the lines in the prior Neighbourhood terminate before the maximum is reached.
Each Neighbourhood is temporally contiguous with the one immediately before and the one after.
Everything transcribed in a single Neighbourhood occurs within that single duration of time, whether it be speech, multimodal action or events happening in the scene.
Relevant actions taking place sequentially or simultaneously are represented in a set of transcript lines using a [Script-based Transcription System](#script).
A Neighbourhood contains all those actions, which are represented using the [Jeffersonian](jefferson.md) or [Mondadaian](mondada.md) conventions, sometimes in concurrent [Subtiers](tiers.md).

See also [HEAD](#head).

### Non-Sequential Overlap <a id='ns-overlap'></a>

Sometimes, speakers or actions may overlap in duration but are not sequentially relevant to each other.
For example, two separate groups (A and B) are speaking at the same time in a room, so that the speech of one person in group A is inadvertently overlapping with another speaker in group B.
In _DOTE_, this is marked with matching single curly brackets -- `{non-sequential overlap}` -- on more than one line in a [Neighbourhood](#neighbourhood).

### Overlap <a id='overlap'></a>

Overlaps between speakers are traditionally marked between matching single square brackets -- `[overlap]` -- on more than one line in a [Neighbourhood](#neighbourhood).

See [Non-Sequential Overlap](#ns-overlap).

### Pan <a id='pan'></a>

[Video-cues](cues.md) can initiate a transition between one view of the video and another that is displayed in the [Viewport](#viewport) of a [Video Panel](#video).
A Pan transition smoothly and linearly tracks between an initial view of the video and a target view.
This is only true if the same media is selected and [Smooth Transition](#smooth) is selected.

See also [Zoom](#zoom) and [Jump Cut](#jump-cut).

### Play Transport <a id='play'></a>

The Play Transport consists of the media controls that affect [Playback](play.md).

### Projection <a id='projection'></a>

A Projection is a rendering of a [360-degree Video](#360) recording onto a 2D rectangular Viewport by mapping geometrical perspective according to a specific algorithm.
Like with printed world maps/atlases -- not globes -- each Projection [enhances certain features and distorts others](https://en.wikipedia.org/wiki/Map_projection#Distortion).

See [Equirectangular](#equi).

### Project <a id='project'></a>

A _DOTE_ [Project](project.md) consists of all temporally synchronised [Media](media.md) and all Transcripts associated with one continuous event.

### Proportional Timing Interval <a id='pti'></a>

A Proportional Timing Interval is a non-standard method to indicate durations of time in a Transcript.
_DOTE_ supports a special Unicode symbol to indicate 0.1 seconds: `◘`.
This symbol indicates the passing of 0.1 seconds, eg. `◘◘◘◘◘` = 0.5 seconds.
It is especially useful in the [Mondadaian system](mondada.md) for marking Timing Interval [tiers](tiers.md) in the Head position in a [neighbourhood](#neighbourhood) instead of the more conventional non-proportional 'pause' indications, eg. `(0.1)`.

### Realignment <a id='align'></a>

In qualitative research, the visual layout of transcripts is semantically important, especially for [Overlaps](#overlap) and [Subtiers](tiers.md).
Built in to _DOTE_ is a sophisticated parser that tracks vertical alignment within and across [Neighbourhoods](#neighbourhood) in both [Jeffersonian](jefferson.md) and [Mondadaian](mondada.md) systems.
When something goes out of alignment, _DOTE_ can indicate this and suggest how to automatically realign everything in a neighbourhood.

### Recam <a id='recam'></a>

[Recamming](https://en.wiktionary.org/wiki/recam) is a term that developed in computer gaming to describe using the virtual cameras in a game to create a novel video narrative based on the game assets.
In DOTE, we support recamming video recordings while transcribing and presenting transcripts using [Video-cues](cues.md).

See [Zoom](#zoom), [Pan](#pan), [Smooth Transition](#smooth) and [Jump Cut](#jump-cut).
See also [Machinima](https://en.wikipedia.org/wiki/Machinima).

### Regular Expression <a id='regex'></a>

A [Regular Expression](find.md#regex) (regex) is a sophisticated system of wildcards and search operators that can structure a search in a [Unicode](#unicode) text, such as a Transcript.

### Rich Text Format (RTF) <a id='rtf'></a>

The Rich Text Format (RTF) is a common, lightweight data structure to represent simple text formatting beyond plain text.
It is readable by most word processors.

### Script-based Transcription System <a id='script'></a>

A Script-based Transcription System denotes a set of conventions and ways of writing that assume that speech (and action) can be written in chunks ([neighbourhoods](#neighbourhood)) of dialogue, much like a play or film script.
The assumption in _DOTE_ is that the script is read from left-to-right and from top-to-bottom.
An alternative is a _score-based_ transcription system that assumes that all speech and action occurs simultaneously in one long, continuous score, comprising subtiers, that notionally continues to infinity, much like a musical score.
This alternative is partially implemented by _DOTE_ in relation to [Subtier Types](#subtier) within a [Neighbourhood](#neigbourhood).
In future releases, an optional, dedicated micro score-based tool will be smartly interchangeable with the script-based system.

### Smooth Transition <a id='smooth'></a>

[Video-cues](cues.md) can initiate a transition between one view of the video and another that is displayed in the [Viewport](#viewport) of a [Video Panel](#video).
A Smooth Transition smoothly and linearly transforms between an initial view of the video and a target view; otherwise there is a sudden transition.

See also [Zoom](#zoom), [Pan](#pan) and [Jump Cut](#jump-cut).

### Spatial Audio <a id='spatial-audio'></a>

Spatial Audio refers to recordings of sound that represent and can be used to reproduce the experience of sound that is spatialised around the hearer to match closely how it would be perceived if one was present in the event recorded at the location of the microphone.
Stereo recordings (2.0) are not really Spatial Audio since they only reproduce the source of sounds along one axis (left/right).

See [Ambisonic](#ambisonic).

### Speaker-id <a id='id'></a>

Every line in the Transcript that has a speaker, including translation and interlinear gloss [Subtier Types](#subtier), requires a unique [Speaker-id in the initial column](transcript.md#id).
Also, every action subtier requires a unique Speaker-id in order to determine the participant/actant that does the action in question.
The Speaker-id can be of a reasonable length from 1 character to 20 characters.
The Speaker-id should only contain letters and numbers (alphanumeric); it should avoid special symbols and punctuation.

### Subtier Type <a id='subtier'></a>

In a modification to the [Mondadaian system](mondada.md), [subtiers](tiers.md) are structured into Types and given names.
The named Subtier Types are assigned to specific speakers or participants, and a unique symbol is assigned to each.
There are four basic Subtier Types: `.translation`, `@gloss`, `/action`, `#category`.

### Subtitle <a id='subtitle'></a>

`DOTE` can [generate and export Subtitles](export.md) derived from the Transcript in the Editor.
These subtitles are in a file in `SRT` format and can be overlaid on the video by most external media players during playback.

### Sync-code <a id='sync-code'></a>

In order to anchor the Transcript text to the media from which it is derived, [Sync-codes](sync-code.md) can be created that tie the timecode on the [Timeline](timeline.md) to a specific line in the Transcript.

See also [CS-mode](#cs-mode).

### Synchronised Media <a id='sync'></a>

_DOTE_ assumes that in a specific Project, all [imported Media](media.md) are already synchronised to the same start point and end point in time in relation to the original recorded event.
This must be undertaken externally in a video editor prior to importing.

### Technical Comment <a id='tech-comment'></a>

A Technical Comment is a comment on the structure of the Transcript itself.
It is specific to _DOTE_, but is found in some programming languages as well.
The onset of the comment is marked by `//`, and everything after that on the same line is not a part of the Transcript.
Thus, a transcriber can mark up the Transcript line-by-line with brief meta-messages about the process of editing the Transcript or interesting phenomena.
Consecutive Technical Comments at the beginning of the Transcript are treated as a simple form of meta-data.
Technical Comments can be hidden when [exporting the Transcript to RTF or Subtitles](export.md).

Cf. [Comment](#comment).

### Tier <a id='tier'></a>

A Tier in a Transcript is a line in a [Neighbourhood](#neighbourhood) that is dedicated to representing one specific phenomena or event, such as the speech, eye gaze or hand movements of one speaker.

See [Subtier Type](#subtier).

### Timecode (or Timestamp) <a id='timecode'></a>

A Timecode is a temporal reference to a specific moment in a playable media file, starting at 0:00:00.0 `[hour:min:sec.tenth_of_sec]`.

See [Sync-code](sync-code.md) and [Video-cue](cues.md) that both anchor to Timecodes.

### Timeline <a id='timeline'></a>

The [Timeline](timeline.md) is a linear graphical representation of time passed in a Project.

See [Waveform](#waveform) and [Timecode](#timecode).

### Timing interval <a id='interval'></a>

Intervals of time can be marked explicitly in a transcription system.
In the [Jeffersonian system](jefferson.md), this is commonly represented as a pause indicated by a time duration in single parentheses, eg. `(1.5)` = 1.5 seconds.
In the multimodal [Mondadaian system](mondada.md), the same representation of pauses is used, not only in a speaker tier but also in a dedicated tier in the ([HEAD](#head)) that contains one or more pause indications interspersed by [Alignment Symbols](#align-symbol).
The latter is primarily used to represent the timing of non-verbal actions.
In _DOTE_, this is called a primary Timing Interval tier, since is dedicated to timing intervals.

See also [Proportional Timing Interval](#pti).

### Transcript <a id='transcript'></a>

A Transcript is a specific textual object in _DOTE_ that is created and edited in the [Editor](#editor).

### Transcript Heuristics <a id='heuristics'></a>

_DOTE_ uses a sophisticated parser to interpret the structure of a Transcript.
On that basis, [descriptive Errors and Warnings](errors.md) can be given to help the transcriber conform their Transcript to the standard [Conventions](#conventions) as well as to the special formatting required by _DOTE_.
Moreover, DOTE makes heuristic suggestions to [Realign](#align) [Neighbourhoods](#neighbourhood).

### Unicode <a id='unicode'></a>

[Unicode](https://home.unicode.org) is a global standard for representing languages, symbols and emojis.

### User Interface (UI) <a id='ui'></a>

The [User Interface](ui.md) is the visual (and aural) presentation of the computer application to the user.

### Version Control <a id='version'></a>

[Version Control](versioncontrol.md) is a broad term encompassing all computer systems that track changes in a set of digital documents or media files.

See [Git](#git), [Autobackup](#autobackup) and [Checkpoint](#checkpoint).

### Video-cue <a id='video-cue'></a>

A [Video-cue](cues.md) is a unique point on the [Timeline](timeline.md) that indicates that a change in the [Viewport](#viewport) of a [Video Panel](video.md) is to be performed.
This function automates the presentation of media during [Playback](play.md) in a more cinematic fashion.
A limited set of virtual [Recam](#recam) camera movements are supported.

See also [Zoom](#zoom), [Pan](#pan), [Smooth Transition](#smooth) and [Jump Cut](#jump-cut).

### Video Panel <a id='video-panel'></a>

A [Video Panel](video.md) is a unique panel in the DOTE UI dedicated to displaying a selected video media file according to the user's wishes.
Both 2D and 360-degree video can be displayed in a Video Panel.
Moreover, the video can be zoomed and panned, and transitions can be sudden or smooth when using [Video-cues](cues.md).

See also [Zoom](#zoom), [Pan](#pan), [Smooth Transition](#smooth) and [Jump Cut](#jump-cut).

### Viewport <a id='viewport'></a>

The Viewport is the rectangular portion of the video that is currently visible in the frame of the [Video Panel](#video-panel).

### Warnings and Errors <a id='error'></a>

DOTE can flag [Warnings and Errors](errors.md) in the use of DOTE, as well as in the Editor.

### Waveform <a id='waveform'></a>

In a [Timeline](timeline.md), a waveform representing the amplitude over time of a selected audio track can be displayed.
When imported into a Project using [Media Manager](media.md), the waveform is generated by _DOTE_ by sampling the audio track to convert amplitude into a graphical representation.

### Zoom <a id='zoom'></a>

[Video-cues](cues.md) can initiate a transition between one view of the video and another that is displayed in the [Viewport](#viewport) of a [Video Panel](#video).
A Zoom transition smoothly and linearly tracks between an initial view of the video and a target view by zooming in or out.
This is only true if the same media is selected and [Smooth Transition](#smooth) is selected.

See also [Pan](#pan) and [Jump Cut](#jump-cut).
