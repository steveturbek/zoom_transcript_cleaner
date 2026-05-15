# Zoom Transcript Cleaner

https://turbek.com/zoom_transcript_cleaner/zoom_transcript_cleaner.html

A single HTML file that cleans up Zoom's `meeting_saved_closed_caption.txt` files for use in research and quote extraction. No install, no server, no tracking — open it in a browser and drag the file onto the page.

## What it does

- Removes timestamps and restructures lines into `Speaker: Text` format
- Strips filler words and phrases (Hmm, Yeah, Okay, Sure, Mm-hmm, etc.) at the sentence level — so "I'm not sure." is kept but standalone "Sure." is dropped
- Merges consecutive lines from the same speaker
- Displays the cleaned transcript on the page in interview style — your lines , guest lines normal — in an editable block you can rough-edit before exporting

## Export options

| Button              | What it does                                                                                                                                    |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Download .txt**   | Full `Speaker: Text` conversation, or guest-only plain text (no labels) when the checkbox is on. Guest-only file is named after the guest.      |
| **AI Quote Picker** | Copies the full transcript with a pre-written prompt asking AI to find the 5 most insightful or quotable guest moments. Paste directly into AI. |

## Usage

1. Open `zoom_transcript_cleaner.html` in any modern browser
2. Drop a `meeting_saved_closed_caption.txt` file onto the page
3. Edit the transcript in the preview if needed
4. Use **Copy for Claude** or **Download .txt**
