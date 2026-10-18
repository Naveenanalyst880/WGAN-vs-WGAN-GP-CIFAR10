# WGAN vs WGAN-GP on CIFAR-10

**Student:** Katravath Naveen  
**Roll No.:** 24CS3027  
**Assignment:** DL-078

## Project Overview

This project presents a comparative study of Wasserstein Generative Adversarial Networks (WGAN) using Weight Clipping and Wasserstein GAN with Gradient Penalty (WGAN-GP) on the CIFAR-10 dataset.

The objective is to compare both approaches in terms of training behavior, generator and critic losses, generated image samples, and approximate Fréchet Inception Distance (FID).

The project is inspired by the research paper *Improved Training of Wasserstein GANs* by Gulrajani et al. (2017).

## Objectives

- Implement WGAN with Weight Clipping.
- Implement WGAN-GP with Gradient Penalty.
- Train both models on CIFAR-10.
- Compare training losses and generated image samples.
- Evaluate image quality using approximate FID scores.

## Project Structure

```text
WGAN_GP_24CS3027_Final_Submission_Package/
├── WGAN_WGAN_GP_24CS3027.ipynb
├── IEEE_Final_Report.docx
├── WGAN_vs_WGAN_GP_Presentation.pptx
├── README.md
├── requirements.txt
├── research paper.pdf
├── figures/
│   ├── critic_loss_comparison.png
│   ├── generator_loss_comparison.png
│   ├── wgan_clipping_epoch1.png
│   ├── wgan_clipping_epoch3.png
│   ├── wgan_gp_epoch1.png
│   ├── wgan_gp_lambda5_samples.png
│   └── wgan_gp_samples.png
└── results/
    └── wgan_vs_wgan_gp_results.csv
```

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Google Colab
- CIFAR-10 dataset

## Dataset

CIFAR-10 contains 60,000 color images of size 32 × 32 pixels across 10 classes.

- Training images: 50,000
- Test images: 10,000
- Image channels: RGB

The models use the CIFAR-10 training split for training.

## Methodology

### 1. WGAN with Weight Clipping

The critic's weights are clipped to a fixed range to constrain its behavior and approximate the Lipschitz condition.

### 2. WGAN-GP with Gradient Penalty

Gradient Penalty regularizes the critic by penalizing deviations of the input-gradient norm from 1 at interpolated real and generated samples.

### 3. Evaluation

Both methods are compared using critic loss, generator loss, generated image samples, and approximate FID.

## Main-Run Results

| Metric | WGAN (Clipping) | WGAN-GP |
|---|---:|---:|
| Training epochs | 3 | 3 |
| Approximate FID | 222.05 | 197.23 |

In this run, WGAN-GP obtained a lower approximate FID than WGAN with Weight Clipping. This is a preliminary result and does not establish that WGAN-GP will perform better in every setting.

**Important:** FID was estimated using 500 real and 500 generated images. The short training duration and limited evaluation sample size should be considered when interpreting the results.

## How to Run

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload `WGAN_WGAN_GP_24CS3027.ipynb` or open it from Google Drive.
3. Select **Runtime → Change runtime type** and choose GPU if available.
4. Run the notebook cells in order.
5. Review the generated image samples, loss plots, and FID comparison.

Training time depends on the available hardware.

## Repository Files

- **Notebook:** Implementation and experiments.
- **Final Report:** Project methodology, results, and discussion.
- **Presentation:** Slides for project presentation.
- **Figures:** Training plots and generated image samples.
- **Results CSV:** Main-run results table.
- **Research Paper:** Reference paper used for the project.

## Limitations

- Training was limited to three epochs per method.
- FID was estimated using only 500 real and 500 generated images.
- Results are based on the reported run and have not been established across multiple random seeds.
- The implementation is a simplified comparative study, not an exact reproduction of every experiment in the original research paper.

## Reference

Gulrajani, I., Ahmed, F., Arjovsky, M., Dumoulin, V., and Courville, A., “Improved Training of Wasserstein GANs,” *Advances in Neural Information Processing Systems (NeurIPS)*, 2017.

Paper: https://arxiv.org/abs/1704.00028

---

**Author:** Katravath Naveen  
**Roll No.:** 24CS3027  
**Assignment:** DL-078
