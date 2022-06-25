## Glossary of key terms in _DOTE_

Below is a list of key terms in alphabetical order with short definitions and links to relevant help pages for more information.

### Active Media <a id='active'></a>

When media files are added to a Project using the [Media Manager](media.md) they can be activated to appear in the current Transcript.
If a media file is deactivated, it will not be available for use in the current Transcript.

### Alignment Symbol

An alignment symbol (Mondadian conventions) is a unique symbol reserved for use in a transcript to indicate the temporal alignment of an action in a [subtier](tier.md) with the [HEAD](#head) of the [neighbourhood](#neighbourhood).

See [Realignment](#align).

### Autocompletion

Autocompletion is the automatic, context-sensitive prompting of possible character or symbol strings that the user can select from.
There are several aspects of a Transcript that can be autocompleted in the [Editor](transcript.md).
1. The speaker-id column.
1. Named subtier types: action, translation and gloss.
1. Special symbols and symbol pairs.
1. Overlaps.

### Autosave Backup

DOTE provides a behind-the-scenes automatic backup system called [Autosaving](versioncontrol.md#autosaving).
After a user-defined time interval ([Settings](settings.md)), a new snapshot is taken of the current Transcript if there are unsaved changes.
The Transcript itself is not saved to disk; only a backup copy is made.

### Checkpoint <a id='checkpoint'></a>

A [Checkpoint](versioncontrol.md) is a user-initiated snapshot of the current Transcript if there have been changes made since the last known Checkpoint, regardless of whether or not the Transcript has been saved.
A message can be added to each Checkpoint to log the history of changes in a storied fashion.
Messages are usually in the active, imperative voice, eg. "Edit lines 45-47: add stress and loudness."

### Conventions

### CS Mode

### Editor

### Git

See Version Control and [Checkpoint](#checkpoint).

### HEAD <a id='head'></a>

### Jump Cut

### Loop

### Media Manager

The [Media Manager](media.md) is a tool to add media files in an individual [Project](project.md).
It is used to import, configure and delete media files, as well as make them [active](#active) in the current Transcript.
A Project can contain multiple media files, and each Transcript in a Project can activate one or more of these media to use in the [Timeline](timeline.md) and [Video Panel(s)](video.md).

### Neighbourhood <a id='neighbourhood'></a>

A [Neighbourhood](tiers.md) is a concept we developed to better encapsulate what goes on during simultaneous events captured in a set of transcript lines in a [script-based transcription system](#script).
Sets of lines in a transcript can be grouped together temporally because they try to represent events that happen within a single, continuous duration in time.
Everything transcribed in a Neighbourhood occurs within that single duration of time, whether it be speech, multimodal action or events happening in the scene.
A Neighbourhood contains all those actions, sometimes in concurrent [subtiers](tiers.md), which are represented using the [Jeffersonian](jefferson.md) or [Mondadaian](mondada.md) conventions.

See also HEAD.

### Non-Sequential Overlap <a id='ns-overlap'></a>

### Overlap

See [Non-Sequential Overlap](#ns-overlap).

### Pan

### Play Transport

### Project

### Realignment <a id='align'></a>

### Regular Expression

### Rich Text Format (RTF)

### Script-based Transcription System <a id='script'></a>

### Smooth Transition

### Subtier Type <a id='subtier'></a>

### Subtitles

### Sync-code

### Synchronised Media

### Tier

See [Subtier Type](#subtier).

### Timecode (or Timestamp)

### Timeline

### Timing interval

### Transcript

### Transcript Heuristics

### User Interface (UI)

### Version Control

See [Git](#git) and [Checkpoint](#checkpoint).

### Video-cue

### Video Panel

### Viewport

### Warnings and Errors

### Waveform

### Zoom