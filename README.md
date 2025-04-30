# Reaction-order
# Analyzing Diamonds in the Biosynthetic Network to Show Preferred Reaction Order

This repository contains code and data for analyzing **diamond-shaped motifs** within biosynthetic networks derived from glycans, using all available glycomics datasets within **glycowork**.

Diamond-shaped motifs were specifically chosen to capture contexts where two added monosaccharides are **not directly linked** in the network, thereby enabling the evaluation of **alternative reaction orders**.  
Each motif represents two possible reaction sequences — **A-then-B** and **B-then-A** — leading to a common glycan structure.

An illustration of a diamond motif example is shown below:

<p align="center">
  <img src="https://github.com/user-attachments/assets/245dfdf5-fff5-4d0f-b78b-1a125343f76f" width="300" alt="Diamond Motif Example">
</p>

---

## Workflow Summary

### Motif Extraction
- Diamond-shaped network motifs are extracted using the `find_diamonds` function available in the **network_biosynthesis** module of **glycowork**.

### Reaction and Abundance Extraction
- The `extract_diamond_reactions` function is defined to:
  - Extract reactions stored in motif edges.
  - Couple intermediate abundances with each diamond motif.

### Reaction Order Preference Analysis
- The `collect_reaction_preferences_data` function was implemented to assess preferred reaction paths by:
  - Collecting abundance differences for the two reaction orders.
  - Performing pairwise Welch’s t-tests to evaluate statistical significance.

### Visualization and Interpretation
- Data are summarized in tables and visualized through boxplots, highlighting:
  - Forward vs. reverse path preferences.
  - Distribution of datapoints.
  - Statistical significance indications.

---

## Applications

### Glycan Class-Specific Analysis
Reaction order preferences were analyzed for different glycan classes:
- **N-glycans**
- **O-glycans**
- **Glycosphingolipids (GSLs)**
- **Monosaccharide Oligomers (MOs)**

### Physiological Condition Comparison
Reaction preferences were compared between:
- **Control samples**
- **Tumor samples**

This enabled the evaluation of how physiological conditions may influence biosynthetic reaction order.
