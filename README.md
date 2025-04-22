**High-Resolution VAE-GAN for Cross-Modality Medical Image Synthesis**


**Overview**

This project implements a high-resolution VAE-CycleGAN model designed for cross-modality medical image synthesis — specifically translating between MRI and CT brain scans. It tackles the common challenge of epistemic uncertainty due to small medical datasets by embedding probabilistic modeling in the latent space.


**Key Features**

VAE-CycleGAN Architecture

Combines the generative strength of Variational Autoencoder (VAE) with the domain translation ability of CycleGAN.


Probabilistic Latent Space

Utilizes reparameterization to model uncertainty and improve performance on small datasets.


High-Resolution Output

Integrates RRDBNet (from ESRGAN) for super-resolution and detail enhancement in output images.


Multi-scale Discriminator

Leverages a multi-scale PatchGAN architecture for robust feature learning across multiple resolution levels.


Data Augmentation

Employs augmentation techniques to enhance the diversity and size of the training set.


Dataset

Modalities: CT and MRI brain scan cross-sections


Preprocessing:

Structured into trainA, trainB, testA, and testB folders

Organized for compatibility with standard CycleGAN pipelines

Sources: Multiple medical imaging datasets (properly aggregated and anonymized)


**Model Architecture**

**Generator**

Type: U-Net-based encoder-decoder

Features:

Skip connections for spatial fidelity

Probabilistic latent space (via VAE)

Group normalization

Residual blocks for deeper feature reuse

**Discriminator**

Architecture: Multi-scale PatchGAN

Features:

Operates at 4 different scales

Derivative independence methodology to refine gradient flow

Focuses on both local and global texture fidelity


**Evaluation Metrics & Results**

Metric	Value

BCE Loss (Original vs HR)	0.356623

AUC-ROC Score	0.991677

F1-Score	0.831320

Average PSNR	27.27 dB

Average SSIM	0.891177

**Conclusion**

This project demonstrates the effectiveness of integrating VAE-based probabilistic modeling with adversarial learning for high-resolution, cross-modality medical image translation. The model produces perceptually and quantitatively superior results even with limited training data.
