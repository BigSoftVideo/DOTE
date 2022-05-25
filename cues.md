## Video-cues

A _video-cue_ is a cue to transition to a specific view of the currrent 360 or 2D video at a specific timecode in the video media file.
The idea is to bring a _cinematic experience_ to working with transcripts, such as zoom, pan and jump cut.
This is also called recamming, ie. using a virtual camera to show a different view of the original footage.
Cool! 🍦

[![Video-cues](images/cues/video-cue-edit.png)](images/cues/video-cue-edit.png)

Note that video-cues are independent of [sync-codes](sync-code.md).
Sync-codes index specific lines in the transcript (in the Editor panel) to specific timecodes in the media timeline.
In contrast, video-cues index specific views of the current media source(s) to specific timecodes in the media timeline.
Video-cues have no connection to the Editor, and they are managed on their own timeline.

### Entering and modifying video-cues

1. Open the [media timeline](media.md#media) for the specific video source that is to be cued.
1. Play the video and pause at the point to be video-cued.
1. Adjust the view in the [primary video panel](video.md).
1. Enter a video-cue by clicking on the `ADD VIDEO-CUE` button on the left side of the media timeline.
    - Assign the video-cue to the relevant video media source.
    - In video-cue options, select a _jump cut_ (immediate transition between two views) or a _smooth transition_ (a smooth pan between two views) for the video-cue.
    A smooth transition will track linearly from one view to another over a one second duration.
    This adds a cinematic feel to playing your videos in _DOTE_. Woah! 🎦
    - At any time you can replace the current view for a specific video-cue by selecting the video-cue, altering the view on the primary video panel to your liking, and clicking the `Change View` button.
1. You can drag the video-cue in the timeline to a new time between adjacent video-cues.
    - The video-cue may need to tweaked in order to get the effect desired, eg. a smooth tracking pan/zoom that follows the action.
1. To edit a video-cue, select the desired video-cue on the media timeline, then either press the `MODIFY VIDEO-CUE` button or right click on the video-cue in the relevant timeline.
    - To change a view, select the video-cue first, change the view in the [video panel](video.md), then open the video-cue panel.
    The `Set camera to current view` button will be active.
1. Video-cues can be deleted.
    - Select the video-cue, pen the video-cue panel, and choose `Delete`.
1. The primary and secondary video panels can be independently locked to the bookmarked video-cue.
    - On each video view, click on the video-cue lock button to toggle between locked and free view.
    - The primary video panel is locked and the secondary is unlocked by default.

Please note that edits to video-cues are not tracked by the UI in _DOTE_.
For instance, if you move a video-cue to another position on the timeline, then you cannot undo those actions with the standard shortcuts.
Moreover, video-cues are _not_ tracked by [Checkpoints and Autosaves](versioncontrol.md), so if you revert to an earlier Checkpoint or Autosave, then the video-cues will _not_ be restored to their earlier state.
