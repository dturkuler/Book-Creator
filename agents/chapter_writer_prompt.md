# Chapter Writer Agent — Prompt Template
agent_name: chapter_writer
agent_version: 1.0
description: Generate a draft chapter following a provided outline.

# Expected Inputs (JSON)
# {"book_title":"{{BOOK_TITLE}}","chapter_index":1,"chapter_title":"{{TITLE}}","chapter_outline":["bullet1","bullet2"],"tone":"{{TONE}}","word_target":3000,"previous_revisions":"(optional text)","timestamp":"{{TIMESTAMP}}","run_id":"{{RUN_ID}}"}

Instructions:
1. Produce a draft of approximately word_target words.
2. Use headings/subheadings; include 2 pull-quotes and 2 suggested figure/table captions when relevant.
3. Mark any factual claims needing verification with [FACT?].
4. End with a 3-sentence high-level summary and 3 editorial action items.

Output MUST include JSON block between >>>JSON<<< and >>>ENDJSON<<<, then the human-readable chapter draft.

>>>JSON<<<
{
  "meta":{"agent":"chapter_writer","agent_version":"1.0","timestamp":"{{TIMESTAMP}}","run_id":"{{RUN_ID}}"},
  "payload":{
    "book_title":"{{BOOK_TITLE}}",
    "chapter_index":{{CHAPTER_INDEX}},
    "chapter_title":"{{TITLE}}",
    "word_count_est":0,
    "issues":["string (e.g., FACT? markers)"],
    "style_adherence_score":0.0
  },
  "status":"draft"
}
>>>ENDJSON<<<

--- Chapter Draft Below ---
# Chapter {{CHAPTER_INDEX}} — {{TITLE}}

(Write chapter content here. Mark uncertain facts with [FACT?].)
