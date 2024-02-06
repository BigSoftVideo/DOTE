## Integration with _DOTEbase_

_DOTEbase_ is our new software package that is designed to support qualitative analysis of large audio-visual data sets.

We built it because we wanted a software tools to help researchers to analyse larger corpora of data, either before they have been transcribed or after.

It piggybacks on sets of transcripts created using _DOTE_ that are stored on the same computer or are accessible via an external drive or remote file system.

To use _DOTEbase_, you will need to purchase a license for _DOTE_ from our webshop.

To be able to use _DOTEbase_, you must update _DOTE_ to at least v1.1.0+.
See the help guide for how to install and use DOTEbase.

The main changes to _DOTE_ are as follows:

1. Support for creating, viewing and deleting Transcript Clips in the Transcript panel.
2. Support for importing and exporting Transcripts and Projects with Transcript Clips.
3. Support for importing and exporting Projects with Media Clips.
4. Support for tracking changes to Transcript Clips in Checkpoints and Autobackups.

[![DOTE clipping](images/dotebase/dote-clipping.png)](images/dotebase/dote-clipping.png)

### Making T-clips

1. The first step is to locate the relevant transcript in _DOTE_ that you wish to clip from.
1. Find the relevant lines to be clipped.
1. Select those lines using your mouse by dragging from the onset character/line to the offset character/line.
Clips do not have to start and terminate at the beginning or end of lines.
1. Then select CREATE CLIP in the respective Transcript panel.
1. There are several options to select when creating the clip:
  - Add a comment note
  - Choose the styling (background/foreground colours) and visual style for the clip
  - Add user-defined field names/values
1. Click CREATE and the clip will be inserted and displayed in the Transcript.
1. It will also be added to the list of clips in the current Project.

[![DOTE transcript clipping](images/dotebase/dote-clipping2.png)](images/dotebase/dote-clipping2.png)

This is the same process in _DOTEbase_.
When the Transcript is saved, then the clip will appear in _DOTEbase_ if that Transcript is included in the current DOTEspace.
If the same Transcript is open in both _DOTE_ and DOTEbase, then T-Clips in that Transcript cannot be edited in _DOTEbase_.
_DOTE_ locks the Transcript for editing.
If _DOTE_ is closed or a different Transcript is opened, then the Transcript is released and can be edited again in _DOTEbase_.

T-clips can be edited and deleted.

### Method 1

- Click uniquely inside the T-clip in a transcript panel.
Make sure that the cursor is inside only one clip.
- Select Delete Clip at Cursor.

### Method 2

- Hover over the clip and select the pencil edit or delete icon in the T-clip panel that opens.


Note that Media Clips are not viewable in _DOTE_, only in _DOTEbase_, but the data is stored in each Project.

Note that when a Project/Transcript is open in _DOTE_ the same Transcript in a DOTEspace in _DOTEbase_ will be locked so that it cannot be edited in two places at the same time, which would lead to conflicts.
As soon as a different Transcript is opened in _DOTE_, the previous Transcript will be unlocked in _DOTEbase_, so the relevant clips can be edited again in _DOTEbase_.

Note that users of the Free edition of _DOTE_ will only be able to view Transcript Clips that others have made and shared with them.
They will not be able create nor edit Transcript Clips.
A purchased license will be necessary.
