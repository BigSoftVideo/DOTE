## How to use the undo/redo manager

With v2.0 we have implemented an extra Undo/redo Manager that tracks changes to changes that are more invisible, but which may be desirable to undo, such as underlining, as well as video-cues.

Note that changing anything after performing an Undo will create a completely new stack of actions to Undo because a new future state is being created.
So be careful: make sure that you are happy with the Undo state before making any new changes.
Once you have made a change on top of the Undo state that you have rolled back to, then there is no rolling forward to those old changes that were undone.

### Simple Undo/Redo in the Transcript Editor panel

It is still possible to undo and redo simple textual changes in the Editor panel.
Note that this only applies to changes to the typed text, not underlining, and only to sync-codes if they are repositioned because of a textual edit, eg. a line is inserted or deleted.

- Use the shortcut <kbd>CRTL</kbd> + <kbd>Z</kbd> or  <kbd>⌘</kbd> + <kbd>Z</kbd> on macOS to undo the most recent edit.
- Use <kbd>CRTL</kbd> + <kbd>Y</kbd> or  <kbd>⌘</kbd> + <kbd>Y</kbd> to redo the most recent action that was undone.
- Editing actions can be successively undone step-by-step in reverse order of how they done.

### Opening the Undo Manager

### Rolling back changes

### Redoing changes

### What is NOT tracked by the Undo Manager
