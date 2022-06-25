## Glossary of key terms in _DOTE_

Below is a list of key terms in alphabetical order with short definitions and links to relevant help pages for more information.

### Active Media <a id='active'></a>

When media files are added to a Project using the [Media Manager](media.md) they can be activated to appear in the current Transcript.
If a media file is deactivated, it will not be available for use in the current Transcript.

### Alignment Symbol <a id='align-symbol'></a>

An alignment symbol (Mondadian conventions) is a unique symbol reserved for use in a transcript to indicate the temporal alignment of an action in a [subtier](tier.md) with the [HEAD](#head) of the [neighbourhood](#neighbourhood).

See [Realignment](#align).

### Autocompletion <a id='autocomplete'></a>

Autocompletion is the automatic, context-sensitive prompting of possible character or symbol strings that the user can select from.
There are several aspects of a Transcript that can be autocompleted in the [Editor](transcript.md).
1. The speaker-id column.
1. Named subtier types: action, translation and gloss.
1. Special symbols and symbol pairs.
1. Overlaps.

### Autosave Backup <a id='autosave'></a>

DOTE provides a behind-the-scenes automatic backup system called [Autosaving](versioncontrol.md#autosaving).
After a user-defined time interval ([Settings](settings.md)), a new snapshot is taken of the current Transcript if there are unsaved changes.
The Transcript itself is not saved to disk; only a backup copy is made.

### Checkpoint <a id='checkpoint'></a>

A [Checkpoint](versioncontrol.md) is a user-initiated snapshot of the current Transcript if there have been changes made since the last known Checkpoint, regardless of whether or not the Transcript has been saved.
A message can be added to each Checkpoint to log the history of changes in a storied fashion.
Messages are usually in the active, imperative voice describing the changes made by the new Checkpoint since the last one, eg. "Edit lines 45-47: add stress and loudness."

## Comment <a id='comment'></a>

Cf. [Technical Comment](#tech-comment)

### Conventions <a id='conventions'></a>

### CS Mode <a id='CSmode'></a>

### Editor <a id='editor'></a>

### Git <a id='git'></a>

See Version Control and [Checkpoint](#checkpoint).

### HEAD <a id='head'></a>

### Jump Cut <a id='jump-cut'></a>

### Line number <a id='line-number'></a>

There are two senses of line number in DOTE:

1. The abstract line numbers in the Editor.
The Transcript Editor assigns a temporary, unique number in ascending order to each and every line.
1. The line numbers assigned when the Transcript is exported to an RTF document.
The Exporter can assign a permanent, unique line number to every line or some of the lines according to a principle, such as only assign a line number to a line if it has a speaker, a time interval or a comment.

### Loop <a id='loop'></a>

### Media Manager <a id='media'></a>

The [Media Manager](media.md) is a tool to add media files to an individual [Project](project.md).
It is used to import (by copying), configure and delete media files, as well as make them [active](#active) in the current Transcript.
A Project can contain multiple media files, and each Transcript in a Project can activate one or more of these media to use in the [Timeline](timeline.md) and [Video Panel(s)](video.md).

### Neighbourhood <a id='neighbourhood'></a>

A [Neighbourhood](tiers.md) is a concept we developed to better encapsulate what goes on during simultaneous events captured in a set of transcript lines in a [script-based transcription system](#script).
Sets of lines in a transcript can be grouped together temporally because they try to represent events that happen within a single, continuous duration in time.
Everything transcribed in a Neighbourhood occurs within that single duration of time, whether it be speech, multimodal action or events happening in the scene.
A Neighbourhood contains all those actions, sometimes in concurrent [subtiers](tiers.md), which are represented using the [Jeffersonian](jefferson.md) or [Mondadaian](mondada.md) conventions.

See also [HEAD](#head).

### Non-Sequential Overlap <a id='ns-overlap'></a>

### Overlap <a id='overlap'></a>

See [Non-Sequential Overlap](#ns-overlap).

### Pan <a id='pan'></a>

See also [Video-cue](#video-cue), [Zoom](#zoom), [Pan](#pan), [Smooth Transition](#smooth) and [Jump Cut](#jump-cut).

### Play Transport <a id='play'></a>

### Project <a id='project'></a>

### Realignment <a id='align'></a>

### Regular Expression <a id='regex'></a>

### Rich Text Format (RTF) <a id='rtf'></a>

### Script-based Transcription System <a id='script'></a>

### Smooth Transition <a id='smooth'></a>

### Subtier Type <a id='subtier'></a>

### Subtitle <a id='subtitle'></a>

### Sync-code <a id='sync-code'></a>

### Synchronised Media <a id='sync'></a>

### Technical Comment <a id='tech-comment'></a>

### Tier <a id='tier'></a>

See [Subtier Type](#subtier).

### Timecode (or Timestamp) <a id='timecode'></a>

### Timeline <a id='timeline'></a>

### Timing interval <a id='interval'></a>

### Transcript <a id='transcript'></a>

### Transcript Heuristics <a id='heuristics'></a>

### User Interface (UI) <a id='ui'></a>

### Version Control <a id='version'></a>

See [Git](#git) and [Checkpoint](#checkpoint).

### Video-cue <a id='video-cue'></a>

### Video Panel <a id='video-panel'></a>

### Viewport <a id='viewport'></a>

### Warnings and Errors <a id='error'></a>

### Waveform <a id='waveform'></a>

### Zoom <a id='zoom'></a>
