# py-ptsl

Native Python client for the Pro Tools scripting RPC interface

## Work In Progress

This project is in the very early phases of development (almost nothing works). The 
client successfully connects to Pro Tools, will authorize your connection with your
developer key and a few commands are exposed. PRs and issue submissions are welcome
to guide future development!

## Example

See the examples directory for scripts demonstrating how to use the client.

### session_info.py

This script will print a list of gettable properties from the currently open session.

```sh
$ python3 examples/session_info.py '/path/to/<your api key>.json'  
PTSL Version: 1
Session Name: Untitled
Session Path: Macintosh HD:Users:jamiehardt:Desktop:Untitled:Untitled.ptx
Session Sample Rate: SR_48000
Session Audio Format: FT_WAVE
Session Interleaved: TRUE
Session Timecode Rate: STCR_Fps23976
Session Start Time: 00:57:00:00.00
Session Length: 24:00:00:00
Session Feet+Frames Rate: SFFR_Fps23976
Session Audio Pull Setting: SRP_None
Session Video Pull Setting: SRP_None
Transport State: TS_TransportStopped
Transport Armed: FALSE
Playback Modes: PM_Normal
Record Mode: RM_Normal
```
### print_tracks.py

This script will print a list of every track in the currently open session.

```sh
$ python3 examples/print_tracks.py '/Users/jamiehardt/src/ptsl/Pro Tools Scripting SDK_jamiehardt@me.com.json'  
1:  S    : AudioTrack : A1                               : #ff2a2a2a : {00000000-2a000000-d4cbe0df-2590e43e}
2:       : AudioTrack : A2                               : #ff2a2a2a : {00000000-2a000000-d4cbe0df-ac40203f}
3:       : BasicFolde : Folder 1                         : #ff2a2a2a : {00000000-2a000000-de01e1df-2d2b4575}
4: *SM   : Vca        : VCA 1                            : #ffbc1e0d : {00000000-2a000000-a301e1df-f690ac51}
5: *     : Vca        : VCA 2                            : #ffbc1e0d : {00000000-2a000000-a301e1df-5b0aad51}
6:       : AudioTrack : B1                               : #ff2a2a2a : {00000000-2a000000-d4cbe0df-d3ae273f}
7:    HX : AudioTrack : B2                               : #ff2a2a2a : {00000000-2a000000-d4cbe0df-cc3b283f}
```

## API Coverage

|Command| Implemented | Notes |
| ----- | :---------: | ----- |
|CreateSession| |
|OpenSession|  |
|Import|  |
|GetTrackList| ☑️ |
|SelectAllClipsOnTrack|  |
|ExtendSelectionToTargetTracks|   |
|TrimToSelection|  |
|CreateFadesBasedOnPreset|  |
|RenameTargetTrack|  |
|ConsolidateClip|  |
|ExportClipsAsFiles|  |
|ExportSelectedTracksAsAAFOMF|  |
|GetTaskStatus|  |
|HostReadyCheck| ☑️ |
|RefreshTargetAudioFiles|  |
|RefreshAllModifiedAudioFiles|   |
|GetFileLocation|  |
|CloseSession|  |
|SaveSession|  |
|SaveSessionAs|  |
|Cut|  |
|Copy|  |
|Paste|  |
|Clear|  |
|CutSpecial|  |
|CopySpecial|  |
|ClearSpecial|  |
|PasteSpecial|  |
|ExportMix|  |
|Spot|  |
|ExportSessionInfoAsText|  |
|GetDynamicProperties|  |
|SetPlaybackMode|  |
|SetRecordMode|  |
|GetSessionAudioFormat| ☑️ |
|GetSessionSampleRate| ☑️ |
|GetSessionBitDepth| ☑️ |
|GetSessionInterleavedState| ☑ | [Bug Reported](https://duc.avid.com/showthread.php?p=2658177#post2658177) |
|GetSessionTimeCodeRate| ☑️ |
|GetSessionFeetFramesRate| ☑️ |
|GetSessionAudioRatePullSettings| ☑️ |
|GetSessionVideoRatePullSettings| ☑️ |
|GetSessionName| ☑️ |
|GetSessionPath| ☑️ |
|GetSessionStartTime| ☑️ |
|GetSessionLength| ☑️ |
|SetSessionAudioFormat|  |
|SetSessionBitDepth|  |
|SetSessionInterleavedState|  |
|SetSessionTimeCodeRate|  |
|SetSessionFeetFramesRate|  |
|SetSessionAudioRatePullSettings|  |
|SetSessionVideoRatePullSettings|  |
|SetSessionStartTime|  |
|SetSessionLength|  |
|GetPTSLVersion| ☑️ |
|GetPlaybackMode| ☑️ | Bug to report (see class) |
|GetRecordMode| ☑️ |
|GetTransportArmed| ☑️ |
|GetTransportState| ☑️ |
|AuthorizeConnection| ☑️ |
