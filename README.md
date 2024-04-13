Thank you for your thorough review and detailed comments on our paper.

**Q1**: OOD detection and ID classification are complementary tasks, with labeled ID instances used for training. OOD detection should not compromise ID classification effectiveness, as both are crucial for overall system performance. Most OOD papers include results for both tasks.

**Q2**: The citation [44] refers to the reference by Yang et al. as you mentioned and will be added to the updated version. 

**Q3**: In many existing OOD studies, the OOD data chosen typically have non-overlapping categories with the ID data, an approach that does not account for more complex real-world scenarios such as covariate shifts and overlapping categories. This limitation has also been highlighted in recent papers at ICML’23 and ICCV’23 [2, 32].

**Q4**: Our approach needs multiple training domains to learn a semantic feature extractor, which ensures consistent semantic interpretation across domains. Notably, our approach does not require domain labels for the training instances, a practical advantage over some DG methods. 

**Q5**: Due to the page limit, we have detailed the neural network design in the Appendix. As outlined in Appendix A.3, we employ a ResNet50 backbone following MBDG's settings. It is important to note that **our proposed method is not dependent on any specific backbone and can be seamlessly integrated with any commonly used deep neural network**. Empirically, we evaluated SODIUM's OOD detection performance against two of the best-performing baselines using two popular backbones in computer vision: VGG16 and WideResNet28-10. On the PACS dataset, the results are as follows:

**AUROC:**

| Backbone | Method | MSP            | Energy         | DDU            | OCSVM          | Avg            |
|----------|--------|----------------|----------------|----------------|----------------|----------------|
| VGG16    | MBDG   | 56.14 ± 4.07   | 60.1 ± 4.7     | 62.32 ± 7.91   | 41.68 ± 4.86   | 55.06 ± 2.56   |
| VGG16    | MEDIC  | NA             | NA             | NA             | NA             | 60.58 ± 3.10   |
| VGG16    | Ours   | 75.06 ± 1.21   | 78.56 ± 1.02   | 66.73 ± 2.31   | 47.92 ± 3.96   | **67.07 ± 1.56**   |
|----------|--------|----------------|----------------|----------------|----------------|----------------|
| WRN28-10 | MBDG   | 62.38 ± 2.43   | 65.88 ± 3.82   | 56.06 ± 5.99   | 47.18 ± 5.06   | 57.88 ± 1.69   |
| WRN28-10 | MEDIC  | NA             | NA             | NA             | NA             | 59.07 ± 1.36   |
| WRN28-10 | Ours   | 67.97 ± 3.51   | 71.74 ± 3.97   | 57.48 ± 5.15   | 46.21 ± 1.71   | **60.85 ± 3.06**   |

**AUPR:**

| Backbone | Method | MSP            | Energy         | DDU            | OCSVM          | Avg            |
|----------|--------|----------------|----------------|----------------|----------------|----------------|
| VGG16    | MBDG   | 16.49 ± 2.63   | 20.27 ± 3.43   | 24.72 ± 4.89   | 14.36 ± 1.78   | 18.96 ± 2.46   |
| VGG16    | MEDIC  | NA             | NA             | NA             | NA             | 21.94 ± 4.15   |
| VGG16    | Ours   | 26.72 ± 3.32   | 30.69 ± 2.0    | 22.19 ± 4.57   | 15.73 ± 4.31   | **23.83 ± 3.43**   |
|----------|--------|----------------|----------------|----------------|----------------|----------------|
| WRN28-10 | MBDG   | 19.55 ± 2.95   | 22.51 ± 4.96   | 18.28 ± 4.69   | 13.62 ± 0.75   | 18.49 ± 3.23   |
| WRN28-10 | MEDIC  | NA             | NA             | NA             | NA             | 18.84 ± 2.59   |
| WRN28-10 | Ours   | 23.41 ± 5.15   | 26.66 ± 7.45   | 19.01 ± 4.7    | 13.31 ± 1.57   | **20.6 ± 4.62**    |

SODIUM consistently outperformed MBDG and MEDIC on both VGG16 and WideResNet28-10 backbones, demonstrating that its superior OOD detection capability is model-agnostic.

**Q6**: This can generate synthetic domains. However, real-world multi-domain datasets such as PACS, VLCS, and TerraIncognita offer diverse, practical challenges that better reflect real-world conditions. 

**Q7**: Semantic OOD detection is conducted on an intra-dataset, with the test set belonging to a single unseen domain. Multiple train domains are needed to train our framework (see Q4). Following a widely recognized strategy, we hold out some classes in PACS and other datasets as OOD classes (Appendix A.5.1).

**Q8**: We wish to emphasize several significant and novel contributions of our work. First, we are pioneers in conducting both theoretical and empirical validations that expose the limitations of the widely used G-invariance (GI) in DG methods, such as MBDG. Furthermore, we have introduced a novel domain invariance principle, Semantic G-invariance (SGI), which has proven more effective than GI in detecting semantic OODs, supported by both theoretical arguments and empirical evidence. We have also developed a novel detection framework that utilizes SGI, establishing a new benchmark in the field. Our extensive empirical evaluations not only validate our approach but also provide valuable insights that could inspire future research in this area.

**Q9**: VOS generates augmented data on the encoded feature space in a single domain to improve the learning of the classification head for OOD detection. It is not suitable to generate diverse synthetic OOD raw images across domains to improve the learning of the semantic feature extractor for semantic OOD detection in unseen domains. 

**Q10**: We will thoroughly review the manuscript.





