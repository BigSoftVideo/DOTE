# _DOTE_ JSON File Formats

Reference for every JSON file that _DOTE_ reads and writes when loading or saving Projects and Transcripts.

---

## Directory Layout

```
<ProjectName>/                   ← Project directory (ProjectPath)
  .project.json                  ← Project descriptor
  .media_clips.json              ← Project-level media clips
  .annotations.json              ← Annotations for media clips
  .tiers.json                    ← Clip tier definitions
  .dotebase_meta.json            ← DOTEbase project metadata
  <video/audio files>            ← Raw media assets

  <TranscriptName>/              ← Transcript subdirectory (TranscriptPath)
    transcript.txt               ← Plain-text transcript (not JSON)
    .transcript.json             ← Transcript descriptor (sync codes, settings, etc.)
    .media_meta.json             ← Media/viewport/cue metadata
    .transcript_clips.json       ← Transcript-level text-range clips
    .annotations.json            ← Annotations for transcript clips
    .dotebase_meta.json          ← DOTEbase transcript metadata
    .autosaves/                  ← Auto-backup snapshots
```

> All filenames beginning with `.` are hidden on disk.

---

## 1. `.project.json` — Project Descriptor

**Location:** Project root directory

```jsonc
{
  // DOTE version that last wrote this file (semver string, e.g. "2.0.0-Beta-RC3")
  "projectDescVersion": "string",

  // Ordered list of media files registered to this project
  "projectMedia": [
    {
      // Base filename of the media file (relative to project directory)
      "filename": "string",

      // 0 = VideoFile, 1 = AudioFile
      "fileType": 0,

      // Playback volume in the range [0, 1]
      "volume": 1.0,

      // Whether this media file is muted
      "mute": false,

      // (Video only) Projection type: 0 = Regular2D, 1 = V360Equirect, 2 = AudioOnly
      "videoProjectionType": 0,

      // (360-video only) Projection method: 0 = Equirectangular, 1 = LambertAzimuthal, 2 = Dote
      "v360ProjectionMethod": 2,

      // Legacy field — absolute file path used in pre-2.0 files; ignored on write
      "filepath": "string | undefined"
    }
  ],

  // Legacy fields — kept for backwards compatibility, not actively used
  "videoName": null,             // string | null
  "videoProjection": 0,          // VideoProjectionType enum value
  "videoDisplayProjection": 2    // V360ProjectionMethod enum value
}
```

---

## 2. `.transcript.json` — Transcript Descriptor

**Location:** Transcript subdirectory

```jsonc
{
  // DOTE version that last wrote this file
  "doteVersion": "string",

  // Font size for the Monaco code editor.
  // kind 0 = use global settings default; kind 1 = overridden per-transcript
  "fontSize": {
    "kind": 0,           // 0 = Default, 1 = Overridden
    "defaultValue": 12,  // Used when kind = Default
    "value": 14          // Used when kind = Overridden (field absent when kind = Default)
  },

  // Width of the speaker-name column (in characters)
  "nameColumnWidth": {
    "kind": 0,
    "defaultValue": 10
  },

  // Whether the right-margin guide line is shown
  "rightMarginVisible": {
    "kind": 0,
    "defaultValue": false
  },

  // Column position of the right-margin guide (character offset)
  "defaultRightMarginPosition": {
    "kind": 0,
    "defaultValue": 70
  },

  // Suppress "missing overlap-end" syntax errors for this transcript
  "ignoreMissingOverlapEndErrors": {
    "kind": 0,
    "defaultValue": false
  },

  // Transcript notation convention: 0 = Jefferson, 1 = Mondada
  "transcriptConventions": 0,

  // Sync codes — map media timecodes to transcript line numbers
  "timeCodes": [
    {
      // Playback time in seconds (undefined only in very old pre-V1.0.0 files)
      "_time": 12.5,

      // 1-based line number in transcript.txt this sync code is attached to
      "_lineNumber": 10,

      // (V2.0.0+) Optional time span covering the associated transcript line
      "_timeRange": {
        "start": 12.5,   // seconds
        "end": 15.3      // seconds
      },

      // Legacy pre-V1.0.0 field: virtual frame number (30fps), superseded by _time
      "_virtualFrameNumber": 375
    }
  ],

  // User-drawn underline decorations in the editor (1-based line/column)
  "userUnderlines": [
    {
      "startLineNumber": 5,
      "startColumn": 1,
      "endLineNumber": 5,
      "endColumn": 20
    }
  ],

  // Language subtier tag strings that are auto-added to new clips
  "autoAddLangSubtiers": ["string"],

  // Gloss subtier tag strings that are auto-added to new clips
  "autoAddGlossSubtiers": ["string"],

  // Per-speaker action subtier configuration
  "actionSubtierProps": [
    {
      "speaker": "string",      // Speaker name this rule applies to
      "subtier": "string",      // Subtier label
      "autoComplete": true,     // Whether subtier is auto-completed on Enter
      "symbol": "string"        // Symbol character used for this action tier
    }
  ]
}
```

---

## 3. `.media_meta.json` — Media & Viewport Metadata

**Location:** Transcript subdirectory

```jsonc
{
  // Whether annotation decorations are visible in the editor
  "showAnnotations": true,

  // Whether syntax-warning highlights are shown
  "showWarnings": true,

  // Whether syntax-error highlights are shown
  "showErrors": true,

  // Whether the current sync-code block is highlighted
  "showCurrentTc": false,

  // Legacy DOTE 1.x field — secondary video panel visibility; not used in 2.0
  "secondaryViewVisible": false,

  // Legacy DOTE 1.x field — primary 360 projection method
  // 0 = Equirectangular, 1 = LambertAzimuthal, 2 = Dote
  "mainVideoDisplayProjection": 2,

  // Legacy DOTE 1.x field — secondary 360 projection method
  "secondaryVideoDisplayProjection": 2,

  // Total known duration of the primary media file (seconds)
  "duration": 0.0,

  // Last playback head position (seconds)
  "currentPlaybackTime": 0.0,

  // Selected time range on the waveform timeline [startSec, endSec]
  "currentSelectionRange": [0.0, 0.0],

  // Per-waveform-panel timeline view ranges, keyed by panel instanceID
  "timelineViewRanges": {
    "1": [0.0, 60.0]   // instanceID → [startSec, endSec]
  },

  // Filenames of media files currently active in this transcript
  "activeMediaFilenames": ["string"],

  // Per-display viewport state (one entry per video/waveform panel)
  "viewportSettings": [
    {
      // Unique panel display ID (e.g. "1", "2", or a waveform instanceID)
      "displayID": "string",

      // Filename of the media file currently shown in this panel
      "currentMediaFilename": "string",

      // (Optional) displayID of another panel whose media assignment this mirrors
      "followExisting": "string | undefined",

      // Camera view parameters saved per media file (360-video only)
      "viewControlByVideo": [
        {
          "mediaFilename": "string",
          "viewParameters": {
            "fovY": 1.5708,       // Vertical field of view in radians
            "rotRight": 0.0,      // Camera pitch (rotation around right axis), radians
            "rotUp": 0.0          // Camera yaw (rotation around up axis), radians
          }
        }
      ],

      // View interaction mode: 0 = FollowCues, 1 = SaveView, 2 = FreeLook
      "viewMode": 1,

      // Subtitle overlay settings for this panel
      "subtitleSettings": {
        "srtFilename": null,        // Filename of .srt file in project dir (null = none)
        "fontFamily": "Courier New",
        "fontSize": 8,             // % of canvas height
        "fontColor": "#FFFFFF",
        "showOutline": true,
        "outlineColor": "#898989",
        "outlineWidth": 1,         // % of canvas height
        "showGlow": true,
        "glowColor": "#464646",
        "glowBlur": 4,             // % of canvas height
        "verticalPosition": 85,    // % from top (0 = top, 100 = bottom)
        "maxLineLength": 35,       // max chars per line before wrapping (null = none)
        "enabled": false,
        "minDisplayDuration": 1,   // seconds a subtitle stays visible at minimum
        "allowOverlap": true       // permit stacked/overlapping subtitles
      }
    }
  ],

  // Video cue timeline markers (camera angles / transition points)
  "videoCues": [
    {
      // Filename of the video file this cue references
      "videoFilename": "string",

      // Cue trigger time (seconds)
      "time": 10.0,

      // Transition style: 0 = JumpCut, 1 = Smooth
      "videoTransitionType": 0,

      // Duration of smooth transition (seconds); only present when type = Smooth
      "transitionTime": 2.0,

      // Camera angle at this cue (360-video only)
      "rotUp": 0.0,       // radians
      "rotRight": 0.0,    // radians
      "fovY": 1.5708      // radians
    }
  ]
}
```

---

## 4. `.media_clips.json` — Project Media Clips

**Location:** Project root directory

Top-level value is a **JSON array**. Each element represents one media clip (a time-span selection on the media timeline).

```jsonc
[
  {
    // Unix timestamp (ms) of the last modification
    "lastUpdated": "number",

    // Stable UUID for this clip (uuid v4 string)
    "uuid": "string",

    // Absolute path of the project or transcript that originally created this clip
    "originalParentPath": "string",

    // UUID of a linked transcript clip ("" if none)
    "linkedClipID": "string",

    // Tag names applied to this clip
    "tagNames": ["string"],

    // Names of tiers (sub-categories) this clip belongs to
    "tierNames": ["string"],

    // Filename of the media file this time-span references
    "referenceMediaFilename": "string",

    // The selected time range on the media timeline
    "timeSpan": {
      "lastUpdated": "number",      // Unix ms
      "startTime": 10.5,            // seconds
      "endTime": 15.2,              // seconds (optional — absent for point clips)
      "approximate": false          // true if the boundaries are approximate
    }
  }
]
```

---

## 5. `.transcript_clips.json` — Transcript Text Clips

**Location:** Transcript subdirectory

Top-level value is a **JSON array**. Each element represents one transcript clip (a text-range selection in the editor).

```jsonc
[
  {
    // Unix timestamp (ms) of the last modification
    "lastUpdated": "number",

    // Stable UUID for this clip (uuid v4 string)
    "uuid": "string",

    // Absolute path of the transcript that originally created this clip
    "originalParentPath": "string",

    // UUID of a linked media clip ("" if none)
    "linkedClipID": "string",

    // Tag names applied to this clip
    "tagNames": ["string"],

    // Selected region in the transcript editor (1-based line and column numbers)
    "textRange": {
      "startLineNumber": 5,
      "startColumn": 1,
      "endLineNumber": 6,
      "endColumn": 12
    }
  }
]
```

---

## 6. `.annotations.json` — Clip Annotations

**Location:** Project root directory (for media clips) **and** transcript subdirectory (for transcript clips)
**TypeScript type:** `AnnotationData[]` (`src/types-and-interfaces/clips-datatypes.ts`)

Top-level value is a **JSON array**. Each annotation is associated with exactly one clip via `clipUUID`.

```jsonc
[
  {
    // Unix timestamp (ms) of the last modification
    "lastUpdated": "number",

    // Stable UUID for this annotation (uuid v4 string)
    "UUID": "string",

    // Absolute path of the project/transcript that originally created this annotation
    "originalParentPath": "string",

    // UUID of the clip this annotation is attached to
    "clipUUID": "string",

    // Free-text researcher comment
    "comments": "string",

    // User-defined key/value metadata fields
    "userFields": [
      {
        "lastUpdated": "number",      // Unix ms
        "name": "string",             // Field name (e.g. "Name", "Code")
        "value": "string",            // Field value
        "visibleInClip": true         // Whether this field is shown on the clip card
      }
    ],

    // Visual display properties — shape depends on the 'type' discriminant

    // --- Variant A: No visual (type = 0) ---
    "ui": {
      "type": 0,          // VDPtype.Undefined
      "icon": "string",   // (optional) named icon from ClipIconNames
      "emoji": "string"   // (optional) emoji character
    },

    // --- Variant B: Transcript editor decoration (type = 1) ---
    "ui": {
      "type": 1,                          // VDPtype.Transcript
      "icon": "string",                   // optional
      "emoji": "string",                  // optional
      "useAnnotationHighlight": true,
      // Style of the rough-notation highlight drawn around the text range
      // Allowed values: "underline" | "box" | "circle" | "highlight" | "strike-through" | "crossed-off" | "bracket"
      "annotationHighlightType": "box",
      "highlightColour": "rgb(68, 83, 252)",
      "highlightColourPresetName": "string",  // optional preset name
      "useBackgroundColour": false,
      "backgroundColour": "rgba(68, 83, 252, 0.15)",
      "backgroundColourPresetName": "string", // optional
      // Low-level Monaco editor decoration options (see Monaco IModelDecorationOptions)
      "monacoDecorationOptions": { "zIndex": 2 },
      "inlineClass": "string"             // optional CSS class applied inline
    },

    // --- Variant C: Media waveform decoration (type = 2) ---
    "ui": {
      "type": 2,                          // VDPtype.Media
      "icon": "string",                   // optional
      "emoji": "string",                  // optional
      "useBackgroundColour": false,
      "backgroundColour": "rgba(68, 83, 252, 0.15)",
      "backgroundColourPresetName": "string" // optional
    }
  }
]
```

---

## 7. `.tiers.json` — Clip Tier Definitions

**Location:** Project root directory

Top-level value is a **JSON array**. Tiers are named sub-categories that media clips can belong to.

```jsonc
[
  {
    // Display name of the tier
    "name": "string",

    // Whether this tier is currently visible in the UI
    "visible": true,

    // Optional researcher description of the tier's purpose
    "description": "string",

    // Visual styling for this tier
    "ui": {
      // Hex colour string (e.g. "#FF5733") or null/undefined for no colour
      "colour": "string | null",

      // (Optional) name of a colour preset
      "colourPresetName": "string"
    }
  }
]
```

---

## 8. `.dotebase_meta.json` — DOTEbase Metadata (Project)

**Location:** Project root directory

```jsonc
{
  // Absolute filesystem path of the project when this file was first created.
  // Used to detect whether the project folder has been moved or copied.
  "pathOnCreation": "string",

  // Explicit sort order for the clip panel — array of UUIDs covering both
  // media clips and transcript clips. undefined/null means default sort order.
  "clipSortOrder": ["uuid-string-1", "uuid-string-2"]
}
```

---

## 9. `.dotebase_meta.json` — DOTEbase Metadata (Transcript)

**Location:** Transcript subdirectory

> The same filename is used in both the project root and each transcript subdirectory but contains different data.

```jsonc
{
  // Whether annotation decorations are visible in the transcript editor
  "showAnnotations": true,

  // Whether syntax-warning highlights are shown in the editor
  "showWarnings": false,

  // Whether syntax-error highlights are shown in the editor
  "showErrors": false,

  // Whether the current sync-code line block is highlighted
  "showCurrentSyncCodes": false,

  // Viewport state for each panel associated with this transcript
  // Uses the same ViewportSettings structure as .media_meta.json viewportSettings
  "viewportSettings": [
    {
      "displayID": "string",
      "currentMediaFilename": "string",
      "followExisting": "string | undefined",
      "viewControlByVideo": [
        {
          "mediaFilename": "string",
          "viewParameters": { "fovY": 1.5708, "rotRight": 0.0, "rotUp": 0.0 }
        }
      ],
      "viewMode": 1,
      "subtitleSettings": { /* see .media_meta.json § subtitleSettings */ }
    }
  ]
}
```

---

## Shared Sub-Types

### `OverridableAttribute`

Used in `.transcript.json` for `fontSize`, `nameColumnWidth`, `defaultRightMarginPosition`.
Each setting can either follow the global app preference or be overridden per-transcript.

```jsonc
// Variant A — use global settings default
{ "kind": 0, "defaultValue": 12 }

// Variant B — overridden per-transcript
{ "kind": 1, "value": 16, "defaultValue": 12 }
// kind: 0 = Default, 1 = Overridden
```

### `OverridableToggleAttribute`

Same pattern as `OverridableAttribute` but with boolean values. Used for `rightMarginVisible` and `ignoreMissingOverlapEndErrors`.

```jsonc
{ "kind": 0, "defaultValue": false }
{ "kind": 1, "value": true, "defaultValue": false }
```

### `SyncCodeData`

Element of `timeCodes` array in `.transcript.json`.

```jsonc
{
  "_time": 12.5,           // Timecode in seconds (undefined only in pre-V1.0.0 files)
  "_lineNumber": 10,       // 1-based line number in transcript.txt
  "_timeRange": {          // (V2.0.0+) Optional time span for the line
    "start": 12.5,         // seconds
    "end": 15.3            // seconds
  },
  // Legacy field present only in very old files created before V1.0.0:
  "_virtualFrameNumber": 375  // virtual frames at 30fps, superseded by _time
}
```

### `TextRange`

Used in `userUnderlines` (`.transcript.json`) and `textRange` (`.transcript_clips.json`).
All values are 1-based.

```jsonc
{
  "startLineNumber": 5,
  "startColumn": 1,
  "endLineNumber": 5,
  "endColumn": 20
}
```

### `TimeSpan`

Used inside each entry in `.media_clips.json`.

```jsonc
{
  "lastUpdated": "number",      // Unix ms timestamp
  "startTime": 10.5,            // seconds
  "endTime": 15.2,              // seconds (absent for point-in-time clips)
  "approximate": false          // true if boundaries are estimates
}
```

### `ViewportSettings`

Shared by `viewportSettings` arrays in both `.media_meta.json` and the transcript `.dotebase_meta.json`.

```jsonc
{
  "displayID": "string",             // Panel ID (e.g. "1" for primary video)
  "currentMediaFilename": "string",  // Media file currently loaded in this panel
  "followExisting": "string",        // (Optional) Mirror media from another displayID
  "viewControlByVideo": [            // Saved camera angles, keyed per media file
    {
      "mediaFilename": "string",
      "viewParameters": {
        "fovY": 1.5708,              // Vertical field of view, radians
        "rotRight": 0.0,             // Pitch, radians
        "rotUp": 0.0                 // Yaw, radians
      }
    }
  ],
  "viewMode": 1,                     // 0=FollowCues, 1=SaveView, 2=FreeLook
  "subtitleSettings": { /* SubtitleSettings — see .media_meta.json */ }
}
```
