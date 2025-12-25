# Unpaired Image-to-Image Translation with CycleGAN

This repository reproduces CycleGAN for unpaired image-to-image translation by
implementing the Generator, Discriminator, and full training pipeline from scratch,
based on the original CycleGAN paper.

The project focuses on understanding how cycle-consistency loss contributes to
semantic preservation across domains through hands-on implementation and analysis.

---

## Paper
- Zhu et al., *Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks*
- https://arxiv.org/abs/1703.10593

---

## Task Description
- **Problem**: Unpaired image-to-image translation without paired supervision
- **Setting**: Mapping between two domains using adversarial learning with cycle consistency
- **Objective**: Preserve semantic content while translating visual style

---

## Dataset
- MNIST (grayscale, 1-channel)
- SVHN (RGB, 3-channel)
- Unpaired setting (no one-to-one correspondence between samples)

---

## Method
- CycleGAN architecture with:
  - Two Generators (G: X → Y, F: Y → X)
  - Two Discriminators (D_X, D_Y)
- Loss functions:
  - Adversarial loss
  - Cycle-consistency loss
- Cycle-consistency weight λ = 10

---

## Implementation Details
- Implemented **Generator** and **Discriminator** networks from scratch using PyTorch
- Built the full training pipeline including:
  - Forward translation and cycle reconstruction
  - Loss computation and backpropagation
  - Alternating optimization of generators and discriminators
- Addressed **channel mismatch (1-channel ↔ 3-channel)** between MNIST and SVHN
  by designing asymmetric generator architectures
- Training and experiments are provided in a Jupyter notebook

---

## Evaluation and Analysis
- Qualitative evaluation through generated image samples
- Observed that:
  - Cycle-consistency loss helps preserve digit structure during translation
  - Removing or weakening cycle loss leads to mode collapse or semantic distortion
- Compared translated results across training stages to analyze convergence behavior

---

## Repository Structure
