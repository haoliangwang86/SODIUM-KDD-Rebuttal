Thank you for your thorough review and detailed comments on our paper.

Q1: OOD detection is critical for ensuring the safe operation of deep learning models. However, OOD detection should not compromise ID classification effectiveness, as both ID classification and OOD detection are crucial for the overall system performance. Most OOD papers include results for both tasks.

Q2: The citation [44] refers to “OpenOOD: Benchmarking Generalized Out-of-Distribution Detection”, broken references will be added in the revised version.

Q3: OOD datasets used in existing works typically have non-overlapping categories with the ID data. However, this setting does not account for covariate shifts as the ID train and test data are drawn from the same domain.

Q4: Our approach requires multiple training domains to learn a semantic feature extractor, and to ensure consistent semantic interpretation against domain shifts. Notably, our approach does not require domain labels for the training instances, which is a practical advantage over some domain generalization methods.

Q5: We follow MBDG and use the ResNet50 backbone, as mentioned in Appendix A.3. Our experiment results on additional backbones confirmed SODIUM's superior OOD detection performance across backbones (see [Anonymous Link](https://anonymous.4open.science/r/SODIUM-Rebuttal-5CF9/)).

Q6: While generating synthetic domains is possible, real-world multi-domain datasets, such as PACS, VLCS, and TerraIncognita, offer diverse and practical challenges that better reflect real-world conditions.

Q7: Detailed experimental settings can be found in Appendix A.5.1. Our experiments are conducted under an intra-dataset setting that randomly holds out some classes as OOD. It is a widely recognized strategy in the literature.

Q8: This combination tackles realistic problems and introduces new fundamental challenges. We believe our main contributions: theoretical justification about the limitations of existing DG benchmarks, a new domain invariance principle "SGI: semantic G-invariance,", SGI-based framework design, _etc_., as detailed in Section 1, are significant and novel.

Q9: VOS generates OODs within the feature space of a single domain and, therefore, is incapable of generating diverse OODs across different domains.

Q10: We will thoroughly review the manuscript.

More details are available in [Anonymous Link](https://anonymous.4open.science/r/SODIUM-Rebuttal-5CF9/).
