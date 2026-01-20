## Video-cues

Watch the [basic](https://www.youtube.com/watch?v=g3OEV6xrsTI) and [advanced](https://www.youtube.com/watch?v=zvCNKN2V5dQ) video tutorials on YouTube.

A _video-cue_ is a cue to transition to a specific view of the current 360 or 2D video at a specific timecode in the video media file.
The idea is to bring a _cinematic experience_ to working with transcripts, such as zoom, pan and jump cut.
This is also called _recamming_, ie. using a virtual camera to show a different view of the original footage.
Cool! 🍦

[![Video-cues](images/cues/video-cue-edit.png)](images/cues/video-cue-edit.png)

Note that video-cues are independent of [sync-codes](sync-code.md).
Sync-codes index specific lines in the transcript (in the Editor panel) to specific timecodes in a [Timeline panel](Timeline.md).
In contrast, video-cues index specific views of the current media source(s) to specific timecodes in a Timeline panel.
Video-cues have no connection to the [Transcript Editor](transcript.md), and they are managed on a different layer on a Timeline panel.

Watch the [video tutorial](https://www.youtube.com/watch?v=vCE8AY_HmiU) on YouTube.

### Viewing video-cues <a id='view-cue'></a>

TODO: [![Video-cues](images/cues/video-cue-view.png)](images/cues/video-cue-view.png)

The video-cues can be viewed in a Timeline panel.
The video-cues are signalled by the green 🟢 colour and the clapboard icon 🎬 on the right side of a Timeline.
If there are any video-cues already inserted, then they will appear as inverted green triangles along the top of a Timeline panel.
Clicking the clapboard icon will show/hide the video-cues.

### Adding video-cues <a id='add-cue'></a>

[![Video-cues](images/cues/video-cue-add.png)](images/cues/video-cue-add.png)

1. Make sure that the video-cue tool is open on a [Timeline panel](#view-cue).
2. Select a specific video source in a [Media Player panel](media-panel.md) that shows the video and view that you wish to cue.
3. Turn on the [follow video-cues](media-panel.md#video-tips) button in the same Media Player panel.
4. Play the video and pause at the point to be video-cued.
5. Adjust the viewport in the same [Media Player panel](media-panel.md).
6. Create a new video-cue by clicking on the `ADD VIDEO-CUE` button on the right side of the Timeline panel.
    - Assign the video-cue to the relevant video media source.
    - In video-cue options, select a _jump cut_ (immediate transition between two views) or a _smooth transition_ (a smooth pan between two views) for the video-cue.
    - For the smooth transition, you can select the transition duration (default 2 seconds) and it when created it will appear as green tail line that gets stronger as it approaches the apex of the full transition.
    The length of the tail is proportional to the duration specified.
    A smooth transition will track linearly from one view to another over the user-specified duration.
    This is only really appropriate for transitions within the same video, such as moving from a medium shot to a close-up or panning across the scene of a 360-degree video to show different participants or ongoing actions.
    This adds a cinematic feel to playing your videos in _DOTE_. Woah! 🎦
    - At any time you can replace the current view for a specific video-cue by selecting the video-cue, altering the view on the [Media Player panel](media-panel.md) to your liking, and clicking the `Change View` button that appears in the Media Player panel.
7. You can drag the video-cue in the timeline to a new time between adjacent video-cues.
    - The video-cue may need to tweaked in order to get the effect desired, eg. a smooth tracking pan/zoom that follows the action.
    Sometimes it takes a few iterations to get the desired effect.

If at any time you try to create, edit or move a video-cue when the [follow video-cues](media-panel.md#video-tips) button is not selected, then _DOTE_ will warn you that video-cues will not be tracked in the Media Player panels unless you toggle them on in one or both Media Player panels.

### Editing a video-cue <a id='edit-cue'></a>

There are three ways to edit a video-cue:

1. Select the desired video-cue on the media timeline, then press the `MODIFY VIDEO-CUE` button.

[![Video-cues](images/cues/video-cue-edit2.png)](images/cues/video-cue-edit2.png)

- Using this method means that the viewport should be changed after selecting the video-cue but before pressing the `MODIFY VIDEO-CUE` button, otherwise one cannot change the video-cue to match the selected viewport.

2. Or just right click on the video-cue in the relevant timeline.
This can be useful when playing the video in the relevant video-cue, changing the viewport (no matter what the timecode), and then right clicking on the relevant video-cue.
The video-cue can then be updated with the current viewport in the [Primary Media Player panel](media-panel.md).

3. Alternatively, you can adjust the zoom/pan of the video directly in that Media Player panel and two icons will appear:
    - Apply currently displayed video plus viewport to current video-cue
    - Cancel

#### What can be edited?

- If a viewport in the Primary Media Player panel has been changed, then the `Set camera to current view` button will be active (otherwise it will be greyed out).
Clicking it will change the viewport for the selected video for the current video-cue.

[![Video-cues](images/cues/video-cue-edit3.png)](images/cues/video-cue-edit3.png)

- Video-cues can be deleted.
    - Select the video-cue, open the video-cue panel, and choose `Delete`.
- [Media Player panels](media-panel.md) can be independently locked to the bookmarked video-cue.
    - On each Media Player panel, click on the video-cue lock button as desired.

Please note that edits to video-cues are tracked by the UI in _DOTE_.
For instance, if you move a video-cue to another position on the timeline, then you can undo those actions with the [Undo/Redo](undo.md) function.
Moreover, video-cues are tracked by [Checkpoints and Autobackups](versioncontrol.md), so if you revert to an earlier Checkpoint or Autobackup, then the video-cues will be restored to their earlier state.

TODO: check with @alex that that tracking is enabled now.
