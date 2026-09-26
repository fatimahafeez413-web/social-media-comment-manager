Social Media Comment Manager

An AI automation that reads customer comments on social media, categorizes 
each one, drafts an on-brand reply, and flags anything sensitive (complaints, 
angry comments) for a human to review before anything is sent.

Demo video: [Watch here](https://www.loom.com/share/566be3de4d57449e8af242ef06a48917)

 The problem

Small businesses get flooded with comments on Instagram and Facebook: 
questions, praise, spam, and complaints all mixed together. Business owners 
either spend hours replying to everything by hand, or ignore comments 
entirely, including complaints that need a fast response.

The solution

This automation reads each comment, sorts it into a category (Question, 
Praise, Complaint, Spam, Urgent), and drafts a reply in the business's tone. 
Complaints and urgent comments are always flagged for a human to check, 
so nothing sensitive goes out without approval.

How it works

1. Trigger: Watches a Google Sheet for new or updated comments
2. AI categorization: Sends each comment to Google Gemini with 
   instructions to categorize it and draft a reply, returning structured JSON
3. Parsing:A Python code step extracts the category, reply, and 
   review flag from Gemini's response
4. Write-back: Updates the same row in Google Sheets with the results

 Tech stack

n8n (workflow automation) · Google Gemini API · Google Sheets

 Files in this repository

- social-media-comment-manager.json` — the exported n8n workflow, importable directly into n8n
- sample_comments.csv` — 40 realistic sample comments used for testing

 Results

Tested on 40 sample comments covering questions, praise, complaints, spam, 
and angry messages. [Add your actual count here, e.g. "36 of 40 categorized 
correctly, and 100% of complaints were correctly flagged for human review."]

 Limitations and next steps

- Currently reads from a Google Sheet as a stand-in for real comments; a live 
  version would connect directly to Instagram/Facebook's Comments API, which 
  requires Meta business verification
- No live posting: every reply requires human approval before being sent
- Next steps: connect to a real business account, add a dashboard for 
  reviewing flagged comments, support multiple languages
