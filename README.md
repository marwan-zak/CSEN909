[README.md](https://github.com/user-attachments/files/34859840/README.md)
# From Mistake to Mastery

**CSEN 909 Human Computer Interaction, Winter 2026. Milestone 3: Interactive Prototype**

A browser-based prototype of a teacher-reviewed assessment and learning repair system for Grade 4 mathematics. A pupil uploads a scanned exam, the teacher verifies the extracted text and confirms the grade, and the pupil receives a personalised **Learning Repair Card** with a short retry. The teacher can then check whether the practice helped.

- **Live prototype:** https://marwan-zak.github.io/CSEN909/
- **Repository:** https://github.com/marwan-zak/CSEN909

## Open locally

No installation, build step or external libraries are needed. All assets are local.

1. Download or clone this repository.
2. Open `index.html` in Chrome, Edge, Safari or Firefox.

If your browser blocks local storage when opening the file directly, serve the folder instead:

```
python3 -m http.server 8000
```

then open `http://localhost:8000`.

## Full demonstration

The prototype follows the four primary tasks from Milestone 2. A suggested path through the whole workflow:

1. **Student: upload an exam.** Select *Upload exam*. Choose a JPEG, PNG, WebP or PDF under 4 MB, or choose *Use example paper*. Check the preview, tick the readability box, select the exam language and select *Submit exam*.
2. **Teacher: verify the text.** Use *Switch to Teacher*, then open *Verify text* from the queue. Correct line 2 to `1/2 + 1/3 = 2/5` and line 6 to `2/3 + 2/3 = 4/6`, matching the example paper. Correct only recognition errors and keep the pupil's mathematical mistakes. Confirm all text, then generate suggestions.
3. **Teacher: confirm and release.** Accept the suggested 7/10, or enter another mark with a reason. Confirm or dismiss the support flag. Review the Learning Repair Card (explanation, example and retry question), tick the approval box, optionally edit the message and release.
4. **Student: learn and retry.** Switch back to Student. Open *Messages*, then *See result*, then *Let's try it*. Enter `3/4` and select *Send answer*. A wrong answer gets a supportive hint and can be retried. Then view *My progress*.
5. **Teacher: did the practice help?** In *Class overview*, view the retry result. Load the later-exam example to see the follow-up topic score. A one-question retry and an exam topic score are shown as separate measures.
6. **Language and tour.** Use the EN/DE selector in the header to switch language. The original exam wording is not translated. *Reset demo* clears the workflow and starts again. *Guided tour* plays an automatic captioned walkthrough.

## Features

**Student view**
- Simple home screen with one large upload action
- Photo or file upload with preview, readability check and replace option
- Submission status and notifications
- Result view with grade, feedback and supportive wording (teacher-only severity labels are hidden)
- Learning Repair Card with the pupil's own answer, a visual example and a short retry
- Effort stars and topic progress bars

**Teacher view**
- Review queue of submitted exams
- Side-by-side scan and editable extracted text, with uncertain answers highlighted
- Text confirmation before any grading
- Accept or override the suggested grade (an override requires a reason)
- Recurring mistakes across exams, and confirm or dismiss of support flags
- Edit and approve the Learning Repair Card before release
- Class overview and before/after check of whether practice helped

**General**
- English and German interface
- Responsive layout for desktop, tablet and narrow screens

## Scope and limitations

This is a UI prototype, as permitted by the course brief.

- OCR, AI grading, recurring-mistake analysis, the extracted answer crop and class data are **simulated** for the supplied fractions example.
- A file you upload is previewed but **not** actually processed by OCR.
- The supported demonstration is one exam. Use *Reset demo* to run it again.
- Other pupils in the class overview are illustrative rows.
- Role switching is a demonstration aid, not authentication. The browser holds the full demo state, so this is not a secure student-record system.
- Use fictional data only. Uploaded files stay in your browser's local storage and are never sent to a server. *Reset demo* clears them.
- Browsers may enforce a storage quota lower than the 4 MB upload limit.
- Camera capture and PDF preview depend on the browser and device.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Page entry point |
| `style.css` | Responsive visual styling |
| `app.js` | Workflow logic, validation, sample data and English/German text |

## Deployment

The site is deployed with GitHub Pages directly from the `main` branch root. There is no build step. To host your own copy, fork or upload these files to a public repository, then enable **Settings > Pages > Deploy from a branch > main > / (root)**.
