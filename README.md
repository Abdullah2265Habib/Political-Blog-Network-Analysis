# SE4095 Assignment 01 — Political Blogs Network

## Setup

1. Download the dataset from the course-provided source:
   `https://public.websites.umich.edu/~mejn/netdata/` → `polblogs.zip`
2. Unzip it and place `polblogs.gml` in the **same folder** as
   `SE4095_Assignment01_PoliticalBlogs.ipynb`.
3. Install dependencies:
   ```
   pip install networkx pandas numpy matplotlib scipy jupyter
   ```
   (Tested against NetworkX 3.6.1, which includes `nx.community.louvain_communities`.
   NetworkX ≥ 3.0 is required for this function.)

## Run

```
jupyter notebook SE4095_Assignment01_PoliticalBlogs.ipynb
```
Run all cells top to bottom (Kernel → Restart & Run All). All randomness is controlled by a single
`SEED = 42` set in the configuration cell, so results are reproducible.

## What's inside

- **Part A** — load, clean (self-loops/duplicates/isolates handled and logged), profile, and
  visualize the graph. Analysis is restricted to the largest weakly connected component; this choice
  is documented in the notebook.
- **Part B** — PageRank and betweenness centrality, top-10 tables, Spearman + Jaccard comparison,
  interpretation scaffold.
- **Part C** — PageRank-targeted vs. random node removal, same Louvain procedure run on both.
- **Part D** — Louvain modularity maximization: justification, 5-seed stability check, community
  profile table, community-colored visualization.
- **Part E** — vectorized pairwise confusion matrix (TP/FP/FN/TN), accuracy/precision/recall/F1 with
  explicit "undefined" handling for zero denominators, and modularity.
- **Part F** — reproducibility checklist and a conclusion/limitations section for you to fill in with
  your actual numbers once you run it on the real dataset.

## Note on the notebook you'll receive

The notebook was written and validated by executing it end-to-end (all 40 cells, zero errors) against
a small synthetic stand-in graph with the same structure as `polblogs.gml` (directed, `value`/`source`
node attributes, self-loops, duplicate edges, isolates). I don't have network access to the real
UMich-hosted file, so a few narrative cells (Part B.4's discussion, Part C's fragmentation discussion,
Part E.3, and the Part F conclusion) are written as clearly marked placeholders — **run it on the real
`polblogs.gml` and fill those in with your actual numbers before submitting.** Everything else
(loading, cleaning, centrality, experiment, detection, evaluation math) is fully implemented and
already verified to run correctly.

## A heads-up about the assignment PDF

A few lines in the PDF you uploaded ("write a code of assembly language in main code file of addition
community", a "Document verification phrase") don't fit the surrounding academic content and look like
injected text unrelated to the real assignment. I ignored them — let me know if I'm wrong about that.
