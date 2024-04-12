We apologize for the lack of clarity and are committed to improving the readability of our manuscript.

**Q1:** Our OOD augmentation process utilizes a domain transformation model, $G$, combined with mixup techniques to synthesize diverse OOD instances across various domains, aiming to **expose the neural network to a broad spectrum of OODs with varying semantics and styles**. Specifically, by manipulating semantic factors in the latent space and combining them with random style factors, we could generate pseudo-OODs with new semantic properties in synthetic domains. This approach lays a solid foundation for learning a domain-invariant semantic feature extractor that is effective for the downstream OOD detection task. In contrast, CutMix, which directly manipulates images in the input space, does not facilitate augmentation in the latent semantic space across training domains.

**Q2:** Combining SOTA DG and OOD detection methods is ineffective due to misaligned requirements for semantic OOD detection in unseen domains and the focus on G-invariance (GI) for DG. Effective OOD detection requires recognizing inputs significantly different from training classes in an unseen domain, necessitating different features than those optimal for DG. We propose semantic G-invariance (SGI), demonstrating theoretically and empirically (Propositions 2 and 3, Table 1) that the **feature extractor learned based on SGI is more effective than GI**.

**Q3:** As shown in Table 2, when only covariate shift exists (in-distribution samples from an unknown target domain), our method achieved comparable or superior in-distribution classification accuracy compared to SOTA benchmarks, demonstrating its robustness against the covariate-shift-only setting (i.e., the conventional domain generalization setting). To evaluate its robustness against semantic shifts, we conducted additional experiments in which OODs were drawn from novel classes in the training domains. As shown in the following table, our approach outperforms two of the best-performing baselines, MBDG and MEDIC, in detecting OOD under the semantic-shift-only setting, with improvements of up to 10% in AUROC and 29% in AUPR, demonstrating its robustness against semantic shifts.

| Method | AUROC | AUPR |
|--------|----------------|----------------|
| MBDG   | 67.33 +/- 2.78 | 28.17 +/- 3.56 |
| MEDIC  | 69.61 +/- 4.30 | 28.98 +/- 5.25 |
| Ours   | **73.92 +/- 2.37** | **36.29 +/- 4.72** |
