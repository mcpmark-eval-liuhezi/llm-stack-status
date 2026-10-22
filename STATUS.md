# LLM Stack Status

This edition was rebuilt from scratch against the live sources - the arXiv abstract page, the paper's PDF, and our Weights & Biases account. Nothing is carried over unverified from the previous edition.

## Paper corner

Citation groundwork for the summarizer blog post's "follows the original Transformer recipe" claim. Source of record: arXiv 1706.03762 (https://arxiv.org/abs/1706.03762).

- **Title, exactly as printed on the arXiv abstract page:** Attention Is All You Need
- **Complete author list, exactly as printed on the arXiv abstract page (8 authors):** Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, Illia Polosukhin

Facts verified from the paper's PDF (https://arxiv.org/pdf/1706.03762 - 15 pages, the current v7 rendering):

- **Scaled dot-product attention is formally defined in subsection 3.2.1, "Scaled Dot-Product Attention", which falls on page 4 of the PDF.** The parent subsection 3.2 "Attention" begins on page 3; 3.2.1 is where the definition Attention(Q, K, V) = softmax(QK^T / sqrt(d_k))V (equation (1)) is given.
- **Figure 1 shows the overall Transformer architecture** ("The Transformer - model architecture.", on page 3; encoder in the left half, decoder in the right). Figure 2, on page 4, is the scaled dot-product attention / multi-head attention diagram pair - the one to cite for attention internals, not for the overall architecture.
- **The word "attention" appears 97 times in the PDF.** This is the complete figure - every match in the whole document, not an estimate: a case-insensitive search of the PDF returns 97 occurrences, of which 93 are the standalone word "attention"/"Attention" and 4 are the plural "attentions". Page-by-page, the matches are distributed 6, 12, 6, 21, 14, 8, 5, 0, 5, 4, 3, 1, 5, 5, 2 across the 15 pages, which sums to 97.

## Telemetry corner

The usual "what's actually in our Weights & Biases account" check.

- The account (entity `hezil6643-modelbest`) does have projects - 18 of them.
- **Not one of them holds any Weave trace data.** All 18 projects were queried directly, and each returned 0 traces.
- With zero traces, **no operations show up at all** (the operation distribution is empty in every project) and **no cost information is captured** - token counts, input/output token totals, and cost fields all come back empty or zero.

Blunt version: nothing there. 18 projects exist, but there are no Weave traces, no logged operations, and no cost data in any of them. If we were assuming the summarizer's tracing was already wired up in W&B, it is not - worth resolving before the blog post goes out.
