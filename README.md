# Codebook

A desktop workspace for coding audio and video in qualitative research, by Panorama Lab. Define a coding protocol, annotate recordings on a timeline, and keep each coder’s work together in a local project folder.

English · [简体中文](README.zh-CN.md)

[Website](https://panorama-lab.com/codebook) · [Download](https://github.com/panorama-lab/codebook/releases) · [Report an issue](https://github.com/panorama-lab/codebook/issues)

## What you can do

- **Build a codebook.** Define tiers with text, number, boolean, single-choice, or multiple-choice values. Document category definitions, inclusion and exclusion criteria, examples, event boundaries, and decision rules. Preview and copy the generated guide, or import and export the structured codebook as JSON.
- **Code recordings in context.** Create time-aligned annotations with a media player, waveform, tier timeline, and coding guide in the same workspace. Adjust interval boundaries, loop selections, change playback speed, and undo or redo edits.
- **Work with multiple coders.** Keep separate annotations for each recording and coder. Track completion and identify completed records that need review after a codebook change.
- **Generate transcripts.** Configure MiniMax transcription to generate timestamped text with speaker labels. Click words to seek to the corresponding recording interval and follow the current word during playback.
- **Keep projects locally.** Media, codebooks, coder identities, annotations, and transcripts live in a project folder you control. Manual coding works offline; automatic transcription requires an internet connection and a provider API key.
- **Choose your interface language.** Use English, Simplified Chinese, or the system language. Changing the interface language leaves research content unchanged.

## Download

Get the application from [GitHub Releases](https://github.com/panorama-lab/codebook/releases). The current download is available for **macOS on Apple Silicon (arm64)**.

Packaged macOS releases check for updates on startup. You can also choose **Codebook → Check for Updates…**. Downloading an update requires confirmation, and installation can be postponed until you are ready to restart.

## Get started

1. **Create a project.** Choose a name and location for a new project folder, or use **File → Open Project** to reopen an existing one.
2. **Define your codebook.** Add tiers and categories, describe the coding procedure, and record the rules coders should follow. You can also import a codebook JSON file. Valid edits save automatically.
3. **Add coders.** Create local coder identities and select the active coder. These identities do not require accounts.
4. **Import recordings.** Add audio or video from **Assets**. Codebook copies the files into the project and checks whether they can be played.
5. **Annotate.** Open a recording to launch its coding window. Drag on a tier to select an interval, then double-click inside the selection to create an annotation. Enter a value and confirm. Use the annotation list or timeline to revisit and edit your work.
6. **Mark the recording complete.** Completion is tracked separately for each coder. Further edits reopen the record; changes to the codebook flag completed records for review.

Each recording/coder pair opens in its own coding window, so you can keep several workspaces open alongside the project window.

## Automatic transcription

Open **Codebook → Settings… → Transcribe**, choose **New provider**, and configure MiniMax with your API key and the `asr-1.0` model. In a recording’s coding window, open the transcript sidebar and choose automatic transcription.

Audio is sent to MiniMax in chunks. Provider usage may incur charges; retrying starts a new run. Failed or canceled transcription leaves the existing transcript intact. Replacing a transcript requires confirmation and archives the previous version in the project.

Transcripts are shared across coders for the same recording. The transcript viewer supports playback navigation; manual proofreading and speaker mapping are not currently available. Speaker labels apply within each audio chunk and do not establish a person’s identity across chunks.

## Project files and backups

A project is a directory of JSON files and imported media:

```text
project.json                 Project identity and format version
codebook.json                Coding protocol, tiers, and categories
coders.json                  Local coder identities
assets/                      Recording metadata
media/                       Imported recordings and extracted audio
coding/                      Annotations organized by recording and coder
transcripts/                 Transcripts and archived versions
.codebook/                   Project lock and generated cache
```

Saved JSON records use atomic replacement and retain the previous version in an adjacent `.bak` file. Back up the entire project folder to preserve both recordings and annotations. Close the project before moving or restoring it; media paths are relative to the project folder.

Multiple app instances or cloud-synced folders must not edit the same project concurrently. Multiple local coder identities provide separate annotation records, rather than live collaboration.

## Current scope

Codebook is in active development. The desktop app currently focuses on audio and video coding. Text-document coding, analytic memos, theme development, coder comparison, and EAF interoperability are not currently available in the desktop workflow.

Playback depends on the recording’s codec. Waveform previews may be unavailable for larger compressed recordings even when playback and coding work. Protocol rules and tier relationships provide guidance; they are not automatically enforced by the timeline.

## Feedback

Use [GitHub Issues](https://github.com/panorama-lab/codebook/issues) for bug reports and feature requests. For playback or annotation problems, include your app version, operating system, media format, and steps to reproduce. Remove API keys and private research material before sharing files.

## Usage

Codebook is currently free for educational use and research purposes.
