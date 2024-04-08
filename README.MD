[//]: # (# Diffusion Models for Image Editing)

<p align="center">
  <img src="./media/title.png" alt="image" style="width:1000px;">
</p>

[![Awesome](media/badge.svg)](https://github.com/SiatMMLab/Awesome-Diffusion-Model-Based-Image-Editing-Methods) 
[![License: MIT](media/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Made With Love](media/Made-With-Love-red.svg)](https://github.com/SiatMMLab/Awesome-Diffusion-Model-Based-Image-Editing-Methods)
[![arXiv](media/arXiv-Paper-red.svg)](https://arxiv.org/abs/2402.17525) 
[![visitors](https://visitor-badge.laobi.icu/badge?page_id=SiatMMLab.Awesome-Diffusion-Model-Based-Image-Editing-Methods)](https://visitor-badge.laobi.icu/badge?page_id=SiatMMLab.Awesome-Diffusion-Model-Based-Image-Editing-Methods)

The repository is based on our survey [Diffusion Model-Based Image Editing: A Survey](https://arxiv.org/pdf/2402.17525.pdf).

Yi Huang*, Jiancheng Huang*, Yifan Liu*, Mingfu Yan*, Jiaxi Lv*, Jianzhuang Liu*, Wei Xiong, He Zhang, Liangliang Cao, Shifeng Chen

Shenzhen Institute of Advanced Technology (SIAT), Chinese Academy of Sciences (CAS), Adobe Inc, Apple Inc, Southern University of Science and Technology (SUSTech)

## Abstract
Denoising diffusion models have emerged as a powerful tool for various image generation and editing tasks, facilitating the synthesis of visual content in an unconditional or input-conditional manner. The core idea behind them is learning to reverse the process of gradually adding noise to images, allowing them to generate high-quality samples from a complex distribution. In this survey, we provide an exhaustive overview of existing methods using diffusion models for image editing, covering both theoretical and practical aspects in the ﬁeld. 
We delve into a thorough analysis and categorization of these works from multiple perspectives, including learning strategies, user-input conditions, and the array of specific editing tasks that can be accomplished.
In addition, we pay special attention to image inpainting and outpainting, and explore both earlier traditional context-driven and current multimodal conditional methods, offering a comprehensive analysis of their methodologies.
To further evaluate the performance of text-guided image editing algorithms, we propose a systematic benchmark, EditEval, featuring an innovative metric, LMM Score.
Finally, we address current limitations and envision some potential directions for future research.

## 🔖 News!!!

📌 We are actively tracking the latest research and welcome contributions to our repository and survey paper. If your studies are relevant, please feel free to contact us.

📰 2024-03-22: The [template](EditEval_v1/Metric/LMM_Score_GPT4V_Prompt_Template.md) of computing LMM Score using GPT-4V, along with a corresponding [leaderboard](#leaderboard) comparing several leading methods, is released.

📰 2024-03-14: Our benchmark [EditEval_v1](#benchmark-editeval_v1) is now released.

📰 2024-03-06: We establish a template for paper submissions. This template is accessible by navigating to the `New Issue` button within `Issues` or by clicking [here](https://github.com/SiatMMLab/Awesome-Diffusion-Model-Based-Image-Editing-Methods/issues/new/choose). Once there, please select the `Paper Submission Form` and complete it following the guidelines provided.

📰 2024-02-28: Our comprehensive survey paper, summarizing related methods published before February 1, 2024, is now available.


## 🔍 BibTeX

```
@article{huang2024diffusion,
  title={Diffusion Model-Based Image Editing: A Survey},
  author={Huang, Yi and Huang, Jiancheng and Liu, Yifan and Yan, Mingfu and Lv, Jiaxi and Liu, Jianzhuang and Xiong, Wei and Zhang, He and Chen, Shifeng and Cao, Liangliang},
  journal={arXiv preprint arXiv:2402.17525},
  year={2024}
}
```



## Table of contents
- [Papers](#papers)
  - <details>
    <summary>Training-Based</summary>
    
    - [Training-Based: Domain-Specific Editing with Weak Supervision](#training-based-domain-specific-editing-with-weak-supervision)
    - [Training-Based: Reference and Attribute Guidance via Self-Supervision](#training-based-reference-and-attribute-guidance-via-self-supervision)
    - [Training-Based: Instructional Editing via Full Supervision](#training-based-instructional-editing-via-full-supervision)
    - [Training-Based: Pseudo-Target Retrieval with Weak Supervision](#training-based-pseudo-target-retrieval-with-weak-supervision)
    </details>
  - <details>
    <summary>Testing-Time Finetuning</summary>
    
    - [Testing-Time Finetuning: Denosing Model Finetuning](#testing-time-finetuning-denosing-model-finetuning)
    - [Testing-Time Finetuning: Embeddings Finetuning](#testing-time-finetuning-embeddings-finetuning)
    - [Testing-Time Finetuning: Guidance with Hypernetworks](#testing-time-finetuning-guidance-with-hypernetworks)
    - [Testing-Time Finetuning: Latent Variable Optimization](#testing-time-finetuning-latent-variable-optimization)
    - [Testing-Time Finetuning: Hybrid Finetuning](#testing-time-finetuning-hybrid-finetuning)
    </details>
  - <details>
    <summary>Training and Finetuning Free</summary>
    
    - [Training and Finetuning Free: Input Text Refinement](#training-and-finetuning-free-input-text-refinement)
    - [Training and Finetuning Free: Inversion/Sampling Modification](#training-and-finetuning-free-inversionsampling-modification)
    - [Training and Finetuning Free: Attention Modification](#training-and-finetuning-free-attention-modification)
    - [Training and Finetuning Free: Mask Guidance](#training-and-finetuning-free-mask-guidance)
    - [Training and Finetuning Free: Multi-Noise Redirection](#training-and-finetuning-free-multi-noise-redirection)
    </details>
- [Benchmark EditEval_v1](#benchmark-editeval_v1)
- [Template of Computing LMM Score](EditEval_v1/Metric/LMM_Score_GPT4V_Prompt_Template.md)
- [Leaderboard](#leaderboard)
- [Star History](#star-history)

    
# Papers
## Training-Based

### Training-Based: Domain-Specific Editing with Weak Supervision
| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [CycleNet: Rethinking Cycle Consistency in Text-Guided Diffusion for Image Manipulation](https://arxiv.org/abs/2310.13165)     | NeurIPS 2023    | 2023.10      |
| [Stylediffusion: Controllable disentangled style transfer via diffusion models](https://openaccess.thecvf.com/content/ICCV2023/papers/Wang_StyleDiffusion_Controllable_Disentangled_Style_Transfer_via_Diffusion_Models_ICCV_2023_paper.pdf)              | ICCV 2023       | 2023.08      |
| [Hierarchical diffusion autoencoders and disentangled image manipulation](https://openaccess.thecvf.com/content/WACV2024/papers/Lu_Hierarchical_Diffusion_Autoencoders_and_Disentangled_Image_Manipulation_WACV_2024_paper.pdf)                   | WACV 2024       | 2023.04      |
| [Towards Real-time Text-driven Image Manipulation with Unconditional Diffusion Models](https://arxiv.org/abs/2304.04344)      | arXiv 2023      | 2023.04      |
| [Fine-grained Image Editing by Pixel-wise Guidance Using Diffusion Models](https://arxiv.org/pdf/2212.02024.pdf)                  | CVPR workshop 2023 | 2022.12   |
| [Diffstyler: Controllable dual diffusion for text-driven image stylization](https://arxiv.org/pdf/2211.10682.pdf)                | TNNLS 2024      | 2022.11      |
| [Diffusion Models Already Have A Semantic Latent Space](https://arxiv.org/pdf/2210.10960.pdf)                                     | ICLR 2022       | 2022.10      |
| [Egsde: Unpaired image-to-image translation via energy-guided stochastic differential equations](https://arxiv.org/pdf/2207.06635.pdf) | NeurIPS 2022 | 2022.07      |
| [Diffusion autoencoders: Toward a meaningful and decodable representation](https://openaccess.thecvf.com/content/CVPR2022/papers/Preechakul_Diffusion_Autoencoders_Toward_a_Meaningful_and_Decodable_Representation_CVPR_2022_paper.pdf)                  | CVPR 2022       | 2021.11      |
| [Unit-ddpm: Unpaired image translation with denoising diffusion probabilistic models](https://arxiv.org/pdf/2104.05358.pdf)       | arXiv 2021      | 2021.04      |
| [Diffusionclip: Text-guided diffusion models for robust image manipulation](https://openaccess.thecvf.com/content/CVPR2022/papers/Kim_DiffusionCLIP_Text-Guided_Diffusion_Models_for_Robust_Image_Manipulation_CVPR_2022_paper.pdf)                 | CVPR 2022       | 2021.01      |


### Training-Based: Reference and Attribute Guidance via Self-Supervision

| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [SmartMask: Context Aware High-Fidelity Mask Generation for Fine-grained Object Insertion and Layout Control](https://arxiv.org/pdf/2312.05039.pdf) | CVPR 2024 | 2023.12 |
| [A Task is Worth One Word: Learning with Task Prompts for High-Quality Versatile Image Inpainting](http://arxiv.org/abs/2312.03594) | arXiv 2023 | 2023.12 |
| [DreamInpainter: Text-Guided Subject-Driven Image Inpainting with Diffusion Models](http://arxiv.org/abs/2312.03771) | arXiv 2023 | 2023.12 |
| [Uni-paint: A Unified Framework for Multimodal Image Inpainting with Pretrained Diffusion Model](https://arxiv.org/abs/2310.07222) | ACM MM 2023 | 2023.10 |
| [Face Aging via Diffusion-based Editing](https://arxiv.org/abs/2309.11321) | BMVC 2023 | 2023.09 |
| [Anydoor: Zero-shot object-level image customization](https://arxiv.org/abs/2307.09481) | CVPR 2024 | 2023.07 |
| [Paste, Inpaint and Harmonize via Denoising: Subject-Driven Image Editing with Pre-Trained Diffusion Model](http://arxiv.org/abs/2306.07596) | arXiv 2023 | 2023.06 |
| [Text-to-image editing by image information removal](https://arxiv.org/abs/2305.17489) | WACV 2024 | 2023.05 |
| [Reference-based Image Composition with Sketch via Structure-aware Diffusion Model](https://arxiv.org/abs/2304.09748) | CVPR workshop 2023 | 2023.04 |
| [Pair-diffusion: Object-level image editing with structure-and-appearance paired diffusion models](https://arxiv.org/abs/2303.17546) | arXiv 2023 | 2023.03 |
| [Imagen editor and editbench: Advancing and evaluating text-guided image inpainting](https://arxiv.org/abs/2212.06909) | CVPR 2023 | 2022.12 |
| [Smartbrush: Text and shape guided object inpainting with diffusion model](https://arxiv.org/abs/2212.05034) | CVPR 2023 | 2022.12 |
| [ObjectStitch: Object Compositing With Diffusion Model](http://arxiv.org/abs/2212.00932) | CVPR 2023 | 2022.12 |
| [Paint by example: Exemplar-based image editing with diffusion models](https://openaccess.thecvf.com/content/CVPR2023/html/Yang_Paint_by_Example_Exemplar-Based_Image_Editing_With_Diffusion_Models_CVPR_2023_paper.html) | CVPR 2023 | 2022.11 |

### Training-Based: Instructional Editing via Full Supervision
| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [SmartEdit: Exploring Complex Instruction-based Image Editing with Multimodal Large Language Models](http://arxiv.org/abs/2312.06739) | CVPR 2024 | 2023.12 |
| [InstructAny2Pix: Flexible Visual Editing via Multimodal Instruction Following](http://arxiv.org/abs/2312.06738) | arXiv 2023 | 2023.12 |
| [Focus on Your Instruction: Fine-grained and Multi-instruction Image Editing by Attention Modulation](http://arxiv.org/abs/2312.10113) | CVPR 2024 | 2023.12 |
| [Emu edit: Precise image editing via recognition and generation tasks](http://arxiv.org/abs/2311.10089) | arXiv 2023 | 2023.11 |
| [Guiding instruction-based image editing via multimodal large language models](http://arxiv.org/abs/2309.17102) | ICLR 2024 | 2023.09 |
| [Instructdiffusion: A generalist modeling interface for vision tasks](https://arxiv.org/abs/2309.03895) | CVPR 2024 | 2023.09 |
| [MoEController: Instruction-based Arbitrary Image Manipulation with Mixture-of-Expert Controllers](https://arxiv.org/abs/2309.04372) | arXiv 2023 | 2023.09 |
| [ImageBrush: Learning Visual In-Context Instructions for Exemplar-Based Image Manipulation](http://arxiv.org/abs/2308.00906) | NeurIPS 2023 | 2023.08 |
| [Inst-Inpaint: Instructing to Remove Objects with Diffusion Models](http://arxiv.org/abs/2304.03246) | arXiv 2023 | 2023.04 |
| [HIVE: Harnessing Human Feedback for Instructional Visual Editing](https://arxiv.org/abs/2303.09618) | CVPR 2024 | 2023.03 |
| [DialogPaint: A Dialog-based Image Editing Model](http://arxiv.org/abs/2303.10073) | arXiv 2023 | 2023.01 |
| [Learning to Follow Object-Centric Image Editing Instructions Faithfully](https://aclanthology.org/2023.findings-emnlp.646/) | EMNLP 2023 | 2023.01 |
| [Instructpix2pix: Learning to follow image editing instructions](https://openaccess.thecvf.com/content/CVPR2023/html/Brooks_InstructPix2Pix_Learning_To_Follow_Image_Editing_Instructions_CVPR_2023_paper.html) | CVPR 2023 | 2022.11 |

### Training-Based: Pseudo-Target Retrieval with Weak Supervision

| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Text-Driven Image Editing via Learnable Regions](https://arxiv.org/abs/2311.16432) | CVPR 2024 | 2023.11 |
| [iEdit: Localised Text-guided Image Editing with Weak Supervision](https://arxiv.org/abs/2305.05947) | arXiv 2023 | 2023.05 |
| [ChatFace: Chat-Guided Real Face Editing via Diffusion Latent Space Manipulation](https://arxiv.org/abs/2305.14742) | arXiv 2023 | 2023.05 |


## Testing-Time Finetuning

### Testing-Time Finetuning: Denosing Model Finetuning

| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Kv inversion: Kv embeddings learning for text-conditioned real image action editing](https://link.springer.com/chapter/10.1007/978-981-99-8429-9_14) | arXiv 2023 | 2023.09 |
| [Custom-edit: Text-guided image editing with customized diffusion models](https://arxiv.org/abs/2305.15779) | CVPR workshop 2023 | 2023.05 |
| [Unitune: Text-driven image editing by fine tuning an image generation model on a single image](https://arxiv.org/abs/2210.09477) | ACM TOG 2023 | 2022.10 |


### Testing-Time Finetuning: Embeddings Finetuning

| Title                                                                                      | Publication            | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Dynamic Prompt Learning: Addressing Cross-Attention Leakage for Text-Based Image Editing](https://openreview.net/forum?id=5UXXhVI08r) | NeurIPS 2023 | 2023.09 |
| [Prompt Tuning Inversion for Text-Driven Image Editing Using Diffusion Models](http://arxiv.org/abs/2305.04441) | ICCV 2023 | 2023.05 |
| [Uncovering the Disentanglement Capability in Text-to-Image Diffusion Models](https://openaccess.thecvf.com/content/CVPR2023/html/Wu_Uncovering_the_Disentanglement_Capability_in_Text-to-Image_Diffusion_Models_CVPR_2023_paper.html) | CVPR 2023 | 2022.12 |
| [Null-text inversion for editing real images using guided diffusion models](https://openaccess.thecvf.com/content/CVPR2023/html/Mokady_NULL-Text_Inversion_for_Editing_Real_Images_Using_Guided_Diffusion_Models_CVPR_2023_paper.html) | CVPR 2023 | 2022.11 |



### Testing-Time Finetuning: Guidance with Hypernetworks

| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [StyleDiffusion: Prompt-Embedding Inversion for Text-Based Editing](https://arxiv.org/abs/2303.15649) | arXiv 2023 | 2023.05 |
| [Inversion-based creativity transfer with diffusion models](https://arxiv.org/abs/2211.13203) | CVPR 2023 | 2022.11 |



### Testing-Time Finetuning: Latent Variable Optimization

| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [StableDrag: Stable Dragging for Point-based Image Editing](https://arxiv.org/abs/2403.04437) | arXiv 2024 | 2024.03 |
| [FreeDrag: Feature Dragging for Reliable Point-based Image Editing](https://arxiv.org/abs/2307.04684) | CVPR 2024 | 2023.12 |
| [Contrastive Denoising Score for Text-guided Latent Diffusion Image Editing](https://arxiv.org/abs/2311.18608) | CVPR 2024 | 2023.11 |
| [MagicRemover: Tuning-free Text-guided Image inpainting with Diffusion Models](https://arxiv.org/abs/2310.02848) | arXiv 2023 | 2023.10 |
| [Dragondiffusion: Enabling drag-style manipulation on diffusion models](https://arxiv.org/abs/2307.02421) | ICLR 2024 | 2023.07 |
| [DragDiffusion: Harnessing Diffusion Models for Interactive Point-based Image Editing](https://arxiv.org/abs/2306.14435) | CVPR 2024 | 2023.06 |
| [Delta denoising score](https://openaccess.thecvf.com/content/ICCV2023/html/Hertz_Delta_Denoising_Score_ICCV_2023_paper.html) | ICCV 2023 | 2023.04 |
| [Directed Diffusion: Direct Control of Object Placement through Attention Guidance](https://arxiv.org/pdf/2302.13153.pdf) | AAAI 2024 | 2023.02 |
| [Diffusion-based Image Translation using disentangled style and content representation](https://arxiv.org/abs/2209.15264) | ICLR 2022 | 2022.09 |


### Testing-Time Finetuning: Hybrid Finetuning

| Title                                                                                      | Publication                | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Forgedit: Text Guided Image Editing via Learning and Forgetting](https://arxiv.org/abs/2309.10556) | arXiv 2023 | 2023.09 |
| [LayerDiffusion: Layered Controlled Image Editing with Diffusion Models](https://arxiv.org/abs/2305.18676) | arXiv 2023 | 2023.05 |
| [Sine: Single image editing with text-to-image diffusion models](https://openaccess.thecvf.com/content/CVPR2023/html/Zhang_SINE_SINgle_Image_Editing_With_Text-to-Image_Diffusion_Models_CVPR_2023_paper.html) | CVPR 2023 | 2022.12 |
| [Imagic: Text-Based Real Image Editing With Diffusion Models](https://openaccess.thecvf.com/content/CVPR2023/html/Kawar_Imagic_Text-Based_Real_Image_Editing_With_Diffusion_Models_CVPR_2023_paper.html) | CVPR 2023 | 2022.10 |



## Training and Finetuning Free

### Training and Finetuning Free: Input Text Refinement

| Title                                                                                      | Publication              | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [User-friendly Image Editing with Minimal Text Input: Leveraging Captioning and Injection Techniques](https://arxiv.org/abs/2306.02717) | arXiv 2023 | 2023.06 |
| [ReGeneration Learning of Diffusion Models with Rich Prompts for Zero-Shot Image Translation](https://arxiv.org/abs/2305.04651) | arXiv 2023 | 2023.05 |
| [InstructEdit: Improving Automatic Masks for Diffusion-based Image Editing With User Instructions](https://arxiv.org/abs/2305.18047) | arXiv 2023 | 2023.05 |
| [Preditor: Text guided image editing with diffusion prior](https://arxiv.org/abs/2302.07979) | arXiv 2023 | 2023.02 |

### Training and Finetuning Free: Inversion/Sampling Modification

| Title                                                                                      | Publication               | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Inversion-Free Image Editing with Natural Language](https://arxiv.org/abs/2312.04965) | CVPR 2024 | 2023.12 |
| [Fixed-point Inversion for Text-to-image diffusion models](https://arxiv.org/abs/2312.12540) | arXiv 2023 | 2023.12 |
| [Tuning-Free Inversion-Enhanced Control for Consistent Image Editing](https://arxiv.org/abs/2312.14611) | arXiv 2023 | 2023.12 |
| [The Blessing of Randomness: SDE Beats ODE in General Diffusion-based Image Editing](https://arxiv.org/abs/2311.01410) | ICLR 2024 | 2023.11 |
| [LEDITS++: Limitless Image Editing using Text-to-Image Models](https://arxiv.org/abs/2311.16711) | CVPR 2024 | 2023.11 |
| [A latent space of stochastic diffusion models for zero-shot image editing and guidance](https://openaccess.thecvf.com/content/ICCV2023/html/Wu_A_Latent_Space_of_Stochastic_Diffusion_Models_for_Zero-Shot_Image_ICCV_2023_paper.html) | ICCV 2023 | 2023.10 |
| [Effective real image editing with accelerated iterative diffusion inversion](https://openaccess.thecvf.com/content/ICCV2023/html/Pan_Effective_Real_Image_Editing_with_Accelerated_Iterative_Diffusion_Inversion_ICCV_2023_paper.html) | ICCV 2023 | 2023.09 |
| [Fec: Three finetuning-free methods to enhance consistency for real image editing](https://arxiv.org/abs/2309.14934) | arXiv 2023 | 2023.09 |
| [Iterative multi-granular image editing using diffusion models](https://arxiv.org/abs/2309.00613) | WACV 2024 | 2023.09 |
| [ProxEdit: Improving Tuning-Free Real Image Editing With Proximal Guidance](https://arxiv.org/abs/2306.05414) | WACV 2024 | 2023.06 |
| [Diffusion self-guidance for controllable image generation](https://arxiv.org/abs/2306.00986) | NeurIPS 2023 | 2023.06 |
| [Diffusion Brush: A Latent Diffusion Model-based Editing Tool for AI-generated Images](https://arxiv.org/abs/2306.00219) | arXiv 2023 | 2023.06 |
| [Null-text guidance in diffusion models is secretly a cartoon-style creator](https://arxiv.org/abs/2305.06710) | ACM MM 2023 | 2023.05 |
| [Negative-prompt Inversion: Fast Image Inversion for Editing with Text-guided Diffusion Models](https://arxiv.org/abs/2305.16807) | arXiv 2023 | 2023.05 |
| [An Edit Friendly DDPM Noise Space: Inversion and Manipulations](https://github.com/inbarhub/DDPM_inversion) | CVPR 2024 | 2023.04 |
| [Training-Free Content Injection Using H-Space in Diffusion Models](https://arxiv.org/abs/2303.15403) | WACV 2024 | 2023.03 |
| [Edict: Exact diffusion inversion via coupled transformations](https://openaccess.thecvf.com/content/CVPR2023/html/Wallace_EDICT_Exact_Diffusion_Inversion_via_Coupled_Transformations_CVPR_2023_paper.html) | CVPR 2023 | 2022.11 |
| [Direct inversion: Optimization-free text-driven real image editing with diffusion models](https://arxiv.org/abs/2211.07825) | arXiv 2022 | 2022.11 |


### Training and Finetuning Free: Attention Modification
| Title                                                                                      | Publication             | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Towards Understanding Cross and Self-Attention in Stable Diffusion for Text-Guided Image Editing](https://arxiv.org/abs/2403.03431) | CVPR 2024 | 2024.03 |
| [HD-Painter: High-Resolution and Prompt-Faithful Text-Guided Image Inpainting with Diffusion Models](https://arxiv.org/abs/2312.14091) | arXiv 2023 | 2023.12 |
| [Tf-icon: Diffusion-based training-free cross-domain image composition](https://arxiv.org/abs/2307.12493) | ICCV 2023 | 2023.07 |
| [Energy-Based Cross Attention for Bayesian Context Update in Text-to-Image Diffusion Models](https://arxiv.org/abs/2306.09869) | NeurIPS 2023 | 2023.06 |
| [Conditional Score Guidance for Text-Driven Image-to-Image Translation](https://arxiv.org/abs/2305.18007) | NeurIPS 2023 | 2023.05 |
| [MasaCtrl: Tuning-Free Mutual Self-Attention Control for Consistent Image Synthesis and Editing](https://arxiv.org/abs/2304.08465) | ICCV 2023 | 2023.04 |
| [Localizing Object-level Shape Variations with Text-to-Image Diffusion Models](https://arxiv.org/abs/2303.11306) | ICCV 2023 | 2023.03 |
| [Zero-shot image-to-image translation](https://dl.acm.org/doi/abs/10.1145/3588432.3591513) | ACM SIGGRAPH 2023 | 2023.02 |
| [Shape-Guided Diffusion With Inside-Outside Attention](https://openaccess.thecvf.com/content/WACV2024/html/Park_Shape-Guided_Diffusion_With_Inside-Outside_Attention_WACV_2024_paper.html) | WACV 2024 | 2022.12 |
| [Plug-and-play diffusion features for text-driven image-to-image translation](https://openaccess.thecvf.com/content/CVPR2023/html/Tumanyan_Plug-and-Play_Diffusion_Features_for_Text-Driven_Image-to-Image_Translation_CVPR_2023_paper.html) | CVPR 2023 | 2022.11 |
| [Prompt-to-prompt image editing with cross attention control](https://openreview.net/forum?id=_CDixzkzeyb) | ICLR 2023 | 2022.08 |


### Training and Finetuning Free: Mask Guidance

| Title                                                                                      | Publication             | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [ZONE: Zero-Shot Instruction-Guided Local Editing](https://arxiv.org/abs/2312.16794) | CVPR 2024 | 2023.12 |
| [Watch your steps: Local image and scene editing by text instructions](https://arxiv.org/abs/2308.08947) | arXiv 2023 | 2023.08 |
| [Energy-Based Cross Attention for Bayesian Context Update in Text-to-Image Diffusion Models](https://arxiv.org/abs/2306.09869) | NeurIPS 2023 | 2023.06 |
| [Differential Diffusion: Giving Each Pixel Its Strength](https://arxiv.org/abs/2306.00950) | arXiv 2023 | 2023.06 |
| [PFB-Diff: Progressive Feature Blending Diffusion for Text-driven Image Editing](https://arxiv.org/abs/2306.16894) | arXiv 2023 | 2023.06 |
| [FISEdit: Accelerating Text-to-image Editing via Cache-enabled Sparse Diffusion Inference](https://arxiv.org/abs/2305.17423) | AAAI 2024 | 2023.05 |
| [Inpaint anything: Segment anything meets image inpainting](https://arxiv.org/abs/2304.06790) | arXiv 2023 | 2023.04 |
| [Region-aware diffusion for zero-shot text-driven image editing](https://arxiv.org/abs/2302.11797) | CVM 2023 | 2023.02 |
| [Text-guided mask-free local image retouching](https://ieeexplore.ieee.org/abstract/document/10219704) | ICME 2023 | 2022.12 |
| [Blended diffusion for text-driven editing of natural images](https://openaccess.thecvf.com/content/CVPR2022/papers/Avrahami_Blended_Diffusion_for_Text-Driven_Editing_of_Natural_Images_CVPR_2022_paper.pdf) | CVPR 2022 | 2021.11 |
| [DiffEdit: Diffusion-based semantic image editing with mask guidance](https://openreview.net/forum?id=3lge0p5o-M-) | ICLR 2023 | 2022.10 |
| [Blended latent diffusion](https://arxiv.org/abs/2206.02779) | SIGGRAPH 2023 | 2022.06 |

### Training and Finetuning Free: Multi-Noise Redirection


| Title                                                                                      | Publication            | Date |
|-------------------------------------------------------------------------------------------|--------------------|--------------|
| [Object-aware Inversion and Reassembly for Image Editing](https://arxiv.org/abs/2310.12149) | ICLR 2024 | 2023.10 |
| [Ledits: Real image editing with ddpm inversion and semantic guidance](https://arxiv.org/abs/2307.00522) | arXiv 2023 | 2023.07 |
| [Sega: Instructing diffusion using semantic dimensions](https://arxiv.org/abs/2301.12247) | NeurIPS 2023 | 2023.01 |
| [The stable artist: Steering semantics in diffusion latent space](https://arxiv.org/abs/2212.06013) | arXiv 2022 | 2022.12 |

# Benchmark EditEval_v1


**EditEval_v1** is a benchmark tailored for evaluation of general diffusion-model based image editing algorithms. It contains 50 high-quality images selected from [Unsplash](https://unsplash.com/), each accompanied by a source text prompt, a target editing prompt, and a text editing instruction generated by GPT-4V. This benchmark covers seven most popular specific editing tasks across semantic, stylistic and structural editing defined in our paper: *object addition*, *object replacement*,  *object removal*, *background change*, *overall style change*, *texture change*, and *action change*. Click [here](EditEval_v1/Dataset) to download this dataset!

# Leaderboard

To facilitate a user-friendly application of LMM Score, [here](EditEval_v1/Metric/LMM_Score_GPT4V_Prompt_Template.md) we provide a comprehensive template for its implementation in GPT-4V. This template comes with step-by-step instructions and all required materials, making it easy for users to apply. Additionally, we construct a leaderboard comparing various representative methods evaluated using LMM Score on our [EditEval_v1](EditEval_v1/Dataset) benchmark, which can be found [here](Leaderboard.md).

# Star History

![Star History Chart](https://api.star-history.com/svg?repos=SiatMMLab/Awesome-Diffusion-Model-Based-Image-Editing-Methods&type=Date)
