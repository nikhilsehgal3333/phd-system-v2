# Method — PDF extraction (adapted from Feynman `pdf-explore`)

For any answer that spans more than one page or section of a PDF: a programme call, a supervisor's
paper, a regulator's guidance, a funding scheme's terms.

The failure this method exists to prevent is answering from the first visible page. Call documents
put eligibility on page 2 and the deadline on page 9; papers put the honest limitation in the
appendix.

## Steps
1. **Map the whole document before extracting.** Title, abstract, structure, methods, figures,
   tables, appendices, references, and for a call: eligibility, required documents, funding,
   language, deadline. Read the PDF with `Read` and its `pages` parameter, in blocks, until the map
   is complete.
2. **Extract with anchors.** Every value, quotation, figure label, and statutory reference keeps its
   page number. An extracted claim without a page number cannot be checked later and will not
   survive verification.
3. **Cross-check anything load-bearing.** A conclusion in an abstract gets checked against the
   methods; a table value against its caption; a cited claim against the cited paper when the
   argument depends on it. Papers overstate their abstracts routinely.
4. **Record what could not be read.** A scanned page, a broken table, a missing appendix — mark it
   `BLOCKED` rather than inferring the contents.
5. **Save the notes.** `programs/<Programme>/research/.drafts/<slug>-pdf-notes.md`, with the source
   path or URL and the extraction date. Findings taken forward carry their labels from
   `phd-system/methods/verification.md`.

For a programme call, the extraction feeds `programs/<Programme>/call.md` directly, and the
deadline and eligibility gates are checked against the live web page as well — a downloaded PDF can
be a stale copy of a call that has since moved.
