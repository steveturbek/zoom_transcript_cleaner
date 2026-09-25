# Zoom Transcript Cleaner

A single HTML file that cleans up Zoom's transcript or `meeting_saved_closed_caption.txt` files for use in research and quote extraction. No install, no server, no tracking — open it in a browser and drag the file onto the page.

https://turbek.com/zoom_transcript_cleaner/zoom_transcript_cleaner.html

# Why

I am interviewing people to make blog posts; transcriptions are very helpful, but the spoken word is so very different than written word.

# What it does

- Removes timestamps and restructures lines into `Speaker: Text` format
- Strips filler words and phrases (Hmm, Yeah, Okay, Sure, Mm-hmm, etc.) at the sentence level — so "I'm not sure." is kept but standalone "Sure." is dropped
- Merges consecutive lines from the same speaker
- Displays the cleaned transcript on the page in interview style — your lines bold, guest lines normal — in an editable block you can rough-edit before exporting

# Observations

- Roughly one sentence in five is a filler reaction, but fillers are only about 3–4% of what was said. The status bar shows this word-based figure (filler sentences plus removed "um"s and "uh"s).

## Export options

| Button              | What it does                                                                                                                                    |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Download .txt**   | Full `Speaker: Text` conversation, or guest-only plain text (no labels) when the checkbox is on. Guest-only file is named after the guest.      |
| **AI Quote Picker** | Copies the full transcript with a pre-written prompt asking AI to find the 5 most insightful or quotable guest moments. Paste directly into AI. |

## To Use

1. Open `zoom_transcript_cleaner.html` in any modern browser
2. Drop a `meeting_saved_closed_caption.txt` file onto the page
3. Edit the transcript in the preview if needed
4. **Download .txt** for continued editing
5. **Copy Speaker Text with AI Quote Finder Prompt**

## Possible future changes

**Filler finder page + `fillers.txt`**

- A second page where you drop 1–10 transcripts. It runs the same parse/clean steps, then ranks what the cleaner is still missing: short leftover sentences (≤4 words, e.g. "exactly."), comma-wrapped phrases (", sort of,", ", I mean,"), and sentence openers ("So, ", "Honestly, "). Each row shows a count, which files it's in, and a sample in context. Filter to "Just me" or "Everyone".
- Move the filler list out of the HTML into `fillers.txt`, one phrase per line, loaded by both pages. The finder page gets a "Download fillers.txt" button that saves the current list plus the phrases you checked, to replace the file on the site.
- Caveats: browsers block reading a neighboring `.txt` when the page is opened as a local file, so keep a built-in copy of the list as a fallback. Both pages need the parse/clean code, so either move it into a shared `.js` file or duplicate it in each page.
- Roughly 200–300 lines of work.
