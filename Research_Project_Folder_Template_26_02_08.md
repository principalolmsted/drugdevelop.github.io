# Research Project Folder Template — Generic Structure

**Date:** February 8, 2026
**For:** Eswar Krishnan, MD

---

## 1. The Core Tension in Your Current IBI355 Structure

Your IBI355 folder uses a **file-type-first** organization at the top level (Documents/, Presentations/, Protocol_and_SAP/, Trial_Data/), but your sub-project STEMI/ breaks this pattern — it organizes **by project** and mixes all file types together (literature PDFs, strategy docs, protocol synopses, presentations, and data files sit side by side).

Both approaches have trade-offs:

| Approach | Strength | Weakness |
|----------|----------|----------|
| **File-type-first** (current top level) | Easy to find "all presentations" or "all protocols" | Fragments a sub-project across 4+ folders |
| **Project-first** (current STEMI) | Everything for one sub-project lives together | Hard to find "all presentations" across sub-projects |

For your workflow — where projects are anchored on molecules/datasets, each with sub-projects that have analysis + manuscript components — **project-first with consistent internal structure** is the stronger choice. Here's why: when you're working on STEMI, you want everything about STEMI in one place. When your CPA needs tax documents, they go to one folder. The same principle applies to your research.

---

## 2. Proposed Generic Template

```
[Molecule_or_Dataset]/
│
├── 00_Resources/                          ← Shared across all sub-projects
│   ├── Literature/                        ← Background papers, guidelines, reviews
│   ├── Competitor_Intel/                  ← Competitive landscape docs
│   ├── Protocols_and_SAPs/                ← Master protocols, SAPs
│   └── Reference_Data/                    ← Shared datasets, reference tables
│
├── 01_[SubProject_Name]/                  ← e.g., 01_Sjogrens_pSS
│   ├── Analysis/                          ← Scripts, notebooks, outputs
│   │   ├── Code/                          ← .py, .jl, .R files
│   │   ├── Data/                          ← Input CSVs, processed data
│   │   └── Outputs/                       ← Figures, tables, HTML reports
│   ├── Manuscript/                        ← Paper drafts, revisions, cover letters
│   │   ├── Drafts/
│   │   ├── Figures/
│   │   └── Submissions/                   ← Final submitted versions
│   ├── Presentations/                     ← Decks related to this sub-project
│   └── Resources/                         ← Sub-project-specific references, lit
│
├── 02_[SubProject_Name]/                  ← e.g., 02_STEMI_Cardioimmunology
│   ├── Analysis/
│   │   ├── Code/
│   │   ├── Data/
│   │   └── Outputs/
│   ├── Manuscript/
│   │   ├── Drafts/
│   │   ├── Figures/
│   │   └── Submissions/
│   ├── Presentations/
│   └── Resources/
│
├── 03_[SubProject_Name]/                  ← e.g., 03_IgG4RD_MITIGATE
│   └── ... (same internal structure)
│
├── Strategy_and_Planning/                 ← CDPs, board narratives, go/no-go docs
│   ├── CDPs/
│   ├── Board_Decks/
│   └── Decision_Analyses/
│
└── Trial_Operations/                      ← Enrollment data, site selection, CRO docs
    ├── Enrollment_Data/
    ├── Site_Selection/
    └── Regulatory/
```

---

## 3. How This Maps to Your IBI355 Content

| Current Location | Proposed Location |
|-----------------|-------------------|
| `Documents/IBI355 pSS Clinical Development Plan*.docx` | `Strategy_and_Planning/CDPs/` |
| `Documents/IBI355 Why CD40L Why Sjogrens Board Narrative.docx` | `Strategy_and_Planning/Board_Decks/` |
| `Documents/IBI355 Multi Criteria Decision Analysis.docx` | `Strategy_and_Planning/Decision_Analyses/` |
| `Documents/IBI355 Monte Carlo Risk Analysis.docx` | `Strategy_and_Planning/Decision_Analyses/` |
| `Documents/Stone et al 2025 Inebilizumab IgG4-RD.pdf` | `03_IgG4RD_MITIGATE/Resources/` |
| `Presentations/IBI355_Sjogrens_Board_Deck.pptx` | `01_Sjogrens_pSS/Presentations/` or `Strategy_and_Planning/Board_Decks/` |
| `Presentations/Spero_IBI355_Fundraising_Deck.pptx` | `Strategy_and_Planning/Board_Decks/` |
| `Protocol_and_SAP/*` | `00_Resources/Protocols_and_SAPs/` |
| `Competitor_Intel/Zenas*.pdf` | `00_Resources/Competitor_Intel/` |
| `STEMI/*.pdf (literature)` | `02_STEMI_Cardioimmunology/Resources/` |
| `STEMI/IBI355 STEMI Clinical Development Plan.docx` | `02_STEMI_Cardioimmunology/Manuscript/Drafts/` or `Strategy_and_Planning/CDPs/` |
| `STEMI/Patient Journey slides.pptx` | `02_STEMI_Cardioimmunology/Presentations/` |
| `STEMI/Supplemental Data*.xlsx` | `02_STEMI_Cardioimmunology/Analysis/Data/` |
| `Trial_Data/*.csv` | `Trial_Operations/Enrollment_Data/` or `01_Sjogrens_pSS/Analysis/Data/` |

---

## 4. Optimality Assessment

### What your current structure does well
- Clear molecule-level anchor (IBI355)
- Numbered prefixes force a display order
- Competitor_Intel and Protocol_and_SAP are cleanly separated

### What could be improved

**Problem 1: Sub-projects don't have consistent internal structure.** STEMI is a flat bucket. If you add a third indication (e.g., lupus nephritis), you'd need to invent the structure again each time. The template above gives you a repeatable skeleton.

**Problem 2: "Documents" is a catch-all.** It currently holds CDPs, board narratives, assessments, executive summaries, preview packages, and CV — these serve very different purposes. Splitting into `Strategy_and_Planning/` (for business docs) vs sub-project-specific `Manuscript/` (for scientific writing) clarifies intent.

**Problem 3: No separation of analysis from manuscript.** Your workflow has a data analysis part and a manuscript part for each sub-project, but these aren't reflected in the folder structure. The `Analysis/` vs `Manuscript/` split within each sub-project matches how you actually work.

**Problem 4: Resources at different scopes aren't distinguished.** A paper about CD40L in atherosclerosis (relevant to STEMI sub-project only) lives alongside Zenas competitor intel (relevant to the whole IBI355 program). The `00_Resources/` (program-wide) vs `[SubProject]/Resources/` (sub-project-specific) distinction solves this.

### Is this the most optimal?

There's no universally optimal structure — it depends on how you access files. But this template optimizes for your stated workflow: project-anchored → sub-project-scoped → separated by work product (analysis vs. manuscript vs. presentation). The main alternative would be the file-type-first approach you partially use now, which works better if you frequently need "all presentations across all sub-projects" but worse for daily sub-project work.

---

## 5. Practical Recommendations

1. **Don't reorganize everything retroactively.** Apply the template to new projects going forward. For IBI355, consider reorganizing only if you're actively working on it.

2. **Create a `_TEMPLATE/` folder** you can duplicate when starting a new project. I can create this for you as a set of empty directories.

3. **The numbered prefix convention (01_, 02_) is worth keeping.** It gives you control over display order and makes the hierarchy scannable.

4. **Keep a `_ARCHIVE/` folder** at the molecule level for superseded versions, old drafts, and files you don't want to delete but don't need in the active tree.

5. **For dataset-anchored projects** (e.g., NHANES analysis, ClinicalTrials.gov enrollment study), the same template works — just replace "molecule" with "dataset" as the top-level anchor:

```
NHANES_Mortality_Analysis/
├── 00_Resources/
├── 01_Sex_Differences_SLE/
│   ├── Analysis/
│   ├── Manuscript/
│   └── ...
├── 02_Death_Certificate_Dimorphism/
│   ├── Analysis/
│   ├── Manuscript/
│   └── ...
└── ...
```
