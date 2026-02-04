# ADC Modeling Automation

Automated CHARMM script for building Antibody-Drug Conjugate (ADC) models with site-specific conjugation.

## What It Does
Automates the manual process of:
- Positioning ligands at specific antibody residues using geometric alignment
- Creating covalent bonds via topological patching
- Removing steric clashes through energy minimization

**Time saved:** ~2 hours of manual setup → <3 minutes automated

## Technical Approach
- **Geometric alignment:** Calculates translation vectors between protein target site and ligand anchor atom
- **Automated patching:** Programmatically applies covalent bond patches
- **Energy relaxation:** Multi-step minimization (SD + ABNR) to resolve clashes

## Usage
```bash
# Configure target residue and segment IDs in the script
charmm < build_adc_complex.inp > output.log
```

## Why Script Instead of GUI?
Traditional tools (Schrodinger, MOE) require manual clicking for each model. This approach enables:
- Reproducible workflows
- Batch processing capability  
- Integration into automated pipelines

## Possible Extensions
The current implementation handles single-site conjugation. The scripting framework can be extended to:
- **Multi-site conjugation:** Loop over multiple residue IDs to generate DAR 2/4/8 models using loop

## Files
- `build_adc_complex.inp` - Main automation script
- Proprietary force field parameters removed for confidentiality

---

Built during ADC modeling work. Feel free to adapt for your own conjugation workflows.
