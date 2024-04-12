Thank you for your valuable feedback and constructive criticism.

We apologize for any lack of clarity in our manuscript due to the page limit and the complex nature of the topic. Based on your comments, we will thoroughly revise the manuscript by:
* Refining notations and formulation
* Ensuring proper introduction and clear explanation of all notations
* Enhancing readability with more detailed explanations throughout the paper
* Updating Table 1's caption and ensuring informative, self-explanatory captions and descriptions for all tables and figures

Regarding your question:
While it is feasible to employ the fitted GDA as an OOD detector, our experiments show that **GDA alone does not deliver satisfactory performance for OOD detection**. Below is a comparison of the AUROC and AUPR scores between a GDA OOD detector and our proposed method on the PACS dataset:

#### AUROC

| Method | env 0  | env 1  | env 2  | env 3  | Avg    |
|--------|-------------------|-------------------|-------------------|-------------------|-------------------|
| GDA    | 53.47 ± 2.66      | 68.52 ± 7.77      | 55.47 ± 1.91      | 53.51 ± 3.04      | 57.74 ± 3.62      |
| Ours   | 75.29 ± 5.21      | 78.23 ± 4.85      | 84.15 ± 3.71      | 79.35 ± 5.11      | **79.25 ± 1.84**      |

#### AUPR

| Method | env 0   | env 1   | env 2   | env 3   | Avg   |
|--------|-------------------|-------------------|-------------------|-------------------|-------------------|
| GDA    | 16.87 ± 3.28      | 25.54 ± 2.97      | 20.64 ± 3.06      | 14.78 ± 5.22      | 19.46 ± 2.36      |
| Ours   | 53.70 ± 1.17      | 53.43 ± 1.47      | 54.77 ± 1.55      | 53.74 ± 3.32      | **53.91 ± 0.29**      |

Our method significantly outperforms the GDA OOD detector.

#### AUROC

| Method               | env 0        | env 1        | env 2        | env 3        | Avg               |
|----------------------|-------------------|-------------------|-------------------|-------------------|-------------------|
| GDA (Training Set ID)| 89.34 ± 1.55      | 92.83 ± 2.61      | 84.33 ± 0.91      | 86.72 ± 2.08      | 88.31 ± 8.7       |

Although GDA struggles with accurately estimating input density outside the training support, it is fairly accurate for in-distribution samples drawn from the training set (see table above). Thus, **GDA is sufficient to screen out "definitely not OOD" samples and accept the "likely OODs" to improve the separability between ID and OOD samples**.
