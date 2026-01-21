Title - "Segment Anything Model with Refined-Prompts for Multimodal Cross-Data Few-shot Medical Image Segmentation". <br />
Authors - Bhumika Adhya, Saptarshi Pani, Irina Shpakovskaya, Dmitrii Kaplun, Ram Sarkar. <br />
Conference - International Symposium on Biomedical Imaging 2026. <br />

Code Files :- <br />
BaseSAM(SamPredictor).ipynb -> Code implementation of the Learnable SAM model used in the study. <br />
ProposedModel.ipynb -> Code implementation of the Proposed model used in the study. <br />

Architecture :- <br />
<img width="1167" height="461" alt="Image" src="https://github.com/user-attachments/assets/404c4d45-cdd6-4d0b-af95-7e7575950f9a" />
<br /><br />
Result Table :- <br />
<img width="812" height="436" alt="image" src="https://github.com/user-attachments/assets/d99efadf-88f8-4669-938b-f6ee17fae256" />
<br /><br />
Result Visualizations :- <br />
1. Segmentation Mask Visualization on KvasirCapsule-SEG Dataset which is trained on Kvasir-SEG Dataset (3-shot) :- <br />
![Image](https://github.com/user-attachments/assets/940874f9-060c-4316-ac6b-6ecdf6ae4d00)
![Image](https://github.com/user-attachments/assets/412398f7-1462-415d-975e-6d019cf1ddd9)
2. Segmentation Mask Visualization on Kvasir-SEG Dataset which is trained on KvasirCapsule-SEG Dataset (3-shot) :- <br />
![Image](https://github.com/user-attachments/assets/c6a0e649-6413-4cba-a0db-cd6dae885d33)
![Image](https://github.com/user-attachments/assets/b71c33b1-83f9-4e95-acd7-c46d889ead5b)
3. Segmentation Mask Visualization on PH2 Dataset which is trained on ISIC 2016 Dataset (3-shot) :- <br />
![Image](https://github.com/user-attachments/assets/616ce8a0-c831-41ee-a457-f80ed0e784a7)
![Image](https://github.com/user-attachments/assets/c6960e63-d74c-4f4e-8ac9-2dd03fc82eab)
4. Segmentation Mask Visualization on ISIC 2016 Dataset which is trained on PH2 Dataset (3-shot) :- <br />
![Image](https://github.com/user-attachments/assets/c30265de-3118-43b8-aab7-a56d60a33e45)
![Image](https://github.com/user-attachments/assets/380442ca-7d16-49a9-82d7-f2ed622bf17d)

Qualitative Results :- <br />
The qualitative improvements observed across successive model variants can be directly attributed to the systematic introduction of generalized adaptation, spatial refinement, semantic grounding, and structural regularization. Starting from the baseline SAM, segmentation masks are highly unstable and poorly aligned with anatomical regions due to the absence of medical domain supervision, resulting in fragmented predictions and weak cross-data generalization. Making SAM learnable under few-shot supervision enables the model to adapt its visual priors to biomedical textures and shapes, yielding substantial gains in lesion localization and overall stability, although predictions remain coarse with imprecise boundaries.

The addition of the U-Net–based Adaptive Mask Refiner further improves results by correcting over-segmentation and boundary leakage through multi-scale spatial reconstruction and skip-connected feature fusion, leading to sharper and more anatomically consistent masks. Subsequently, integrating CLIP-based semantic guidance via cross-attention introduces high-level, dataset-invariant textual priors that resolve semantic ambiguities across datasets, significantly enhancing lesion discrimination and robustness in cross-data settings. Finally, the post-processing stage removes spurious artifacts and enforces anatomical contiguity through morphological operations, resulting in smooth, clinically plausible segmentation masks with reduced variance and the best overall qualitative performance among all variants.
