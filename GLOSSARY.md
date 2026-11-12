# Codebook glossary

English · [简体中文](GLOSSARY_zh-CN.md)

Terminology for Codebook Desktop. Definitions describe the desktop app's concepts; interface wording may vary by context.

## Projects and people

| Term             | Definition                                                                                                  |
| ---------------- | ----------------------------------------------------------------------------------------------------------- |
| Project          | A local collection of media, a codebook, coders, annotations, and transcripts.                              |
| Project archive  | A `.codebook` file used to export, import, and transfer a project.                                          |
| Asset            | An imported audio or video recording to be coded.                                                           |
| Media            | The audio or video content of an asset.                                                                     |
| Coder            | A local identity for the person performing coding, with separate records for each asset.                    |
| Current coder    | The coder whose record is open in a coding window.                                                          |
| Person / People  | Someone represented in an asset who can be associated with annotations or transcript text.                  |
| Source person ID | An identity supplied by transcription or an imported file; it does not by itself identify a project person. |
| Person mapping   | An association between a source identity and a person in the asset.                                         |
| Archived person  | A person retained for existing references but removed from active use.                                      |

## Codebook and rules

| Term                            | Definition                                                                                                               |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Coding                          | Interpreting recorded content and assigning values to time intervals according to a codebook.                            |
| Codebook                        | The project's definitions of tiers, categories, and coding guidance.                                                     |
| Coding protocol                 | The operational criteria and rules that guide coding decisions.                                                          |
| Coding guide                    | The read-only reference in the coding window, drawn from the current tier's saved guidance.                              |
| Tier                            | A named dimension of coding with a value type, optional categories, and guidance. Stored as a `label` in the data model. |
| Category                        | A predefined option in a choice tier. Stored in the tier's `options`.                                                    |
| Value type                      | The form accepted by a tier: text, number, boolean, single choice, or multiple choice.                                   |
| Definition                      | What a category represents and its observable characteristics.                                                           |
| Inclusion conditions            | Evidence required to assign a category.                                                                                  |
| Exclusion conditions            | Conditions that rule out a category or distinguish it from similar categories.                                           |
| Positive example                | A described situation that belongs to a category.                                                                        |
| Negative example                | A described situation that does not belong to a category.                                                                |
| Start criteria / Onset criteria | Observable signals used to decide when an event begins.                                                                  |
| End criteria / Offset criteria  | Observable signals used to decide when an event ends.                                                                    |
| Supplementary rule              | Additional guidance describing its scope, conditions, and handling.                                                      |
| Coding order                    | Guidance on the sequence in which coding should be performed.                                                            |
| Tier relationship               | Guidance on how annotations across tiers relate to one another.                                                          |
| Conflict resolution             | Guidance for deciding between competing interpretations or categories.                                                   |
| Codebook draft                  | Local edits that become project definitions only after a successful save.                                                |

## Annotation and playback

| Term             | Definition                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| Annotation       | A saved value on a tier over a time interval, optionally referencing a person in the data model. |
| Annotation value | The text, number, boolean, or category selection recorded by an annotation.                      |
| Coding record    | The annotations and completion state for one asset/coder pair.                                   |
| Coding window    | The workspace for one project, asset, and coder.                                                 |
| Timeline         | The time-based view of annotations and tier tracks alongside media playback.                     |
| Track            | A timeline row for a visible person and tier.                                                    |
| Waveform         | A visual representation of the audio signal over time.                                           |
| Selection        | The currently selected time interval; selecting an interval alone does not save an annotation.   |
| Boundary         | The start or end time of an annotation interval.                                                 |
| Timestamp        | A position in the recording; annotation times are stored in milliseconds.                        |
| Loop playback    | Repeated playback of the selected interval.                                                      |
| Not started      | The coding record's initial state.                                                               |
| In progress      | Coding is underway or has been reopened by an edit.                                              |
| Complete         | The coder has explicitly marked the record complete, even if it contains no annotations.         |
| Needs review     | A completed record whose reviewed codebook revision differs from the current revision.           |

## Transcription and interchange

| Term                       | Definition                                                                                                                 |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Transcript                 | Timestamped text for an asset, shared across its coders.                                                                   |
| Automatic transcription    | Using a configured service to convert audio into timestamped text.                                                         |
| Transcript segment         | A unit of transcript text with timing and optional source-person information.                                              |
| Word timing                | Timing associated with individual words, when available.                                                                   |
| SRT / SubRip subtitle file | A subtitle format imported as transcript cues with their original text and timestamps.                                     |
| EAF / ELAN annotation file | An XML format from which tier/category definitions or time-aligned annotations can be imported through separate workflows. |
| Category mapping           | Matching imported annotation values to existing codebook categories.                                                       |
| Time adjustment            | An offset in milliseconds added to imported annotation start and end times.                                                |

## AI annotation

| Term                | Definition                                                                                                               |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Provider            | A configured external AI or transcription service and its connection settings. The AI interface also uses “provider”.    |
| Model               | The AI model used by a provider for a task.                                                                              |
| AI annotation       | Model-assisted analysis of selected video, people, tiers, and time range to propose annotations.                         |
| Run                 | One execution of AI annotation, including its requests and saved results.                                                |
| Request             | One model interaction within a run, with its input evidence and response.                                                |
| Frame               | A video image sampled at a particular timestamp for analysis.                                                            |
| Model candidate     | A model-proposed category that is not necessarily accepted or importable.                                                |
| Confidence          | The model's reported certainty for a judgment, rather than a guarantee of correctness.                                   |
| Unresolved          | A judgment without enough evidence or certainty to produce an accepted classification.                                   |
| Boundary search     | Analysis that searches for an event's temporal transition.                                                               |
| Boundary refinement | Analysis that narrows an event's estimated start or end boundary.                                                        |
| Rule verification   | Checking proposed annotations against relevant coding rules.                                                             |
| Verified label      | An AI result that passed the engine's boundary and rule checks and is available for explicit import.                     |
| Coarse-label draft  | An AI result available for import that has not passed complete boundary and cross-tier checks and requires human review. |
| Request budget      | A spending estimate checked between requests, rather than a hard billing cap.                                            |

“Coder” identifies the researcher doing the work; “person” identifies someone in the recording. A “tier” defines a coding dimension, a “category” defines a choice within it, and an “annotation” records a value over time. AI “labels” are proposed results that become annotations when explicitly imported.
