# VideoGPT
Implementation of VideoGPT

https://github.com/wilson1yan/VideoGPT

Steamboat Willie source: https://archive.org/download/steamboat-willie-mickey

VideoGPT utilizes a two-model, two-stage approach

## VQ-VAE (Visual Compression)
Clips from full videos are first used to train a VQ-VAE with 3D Conv layers and axial attention
allowing for a compressed, discrete representation of video data

## Transformer Decoder (Visual Prediction)
The resulting latent codebook is used as a vocabulary for a transformer decoder to learn to model sequences of
video frames in latent space

## Together - VideoGPT
Sequences of discrete latent vectors are predicted/generated by the Transformer Decoder and decoded back into
image space using the pre-trained VQ-VAE decoder

## Possible Improvements to try:
- [ ] Finite Scalar Quantization in place of explicit codebook

This project will require:

- [X] Part 1: VAE (for knowledge/context) - CIFAR10

- [X] Part 2: VQ-VAE/VQ-VAE 2 (Conv2D) - CIFAR10

- [ ] Part 3: (FSQ?) VQ-VAE (Conv3D) - Steamboat Willie

- [ ] Part 4: Transformer Decoder - latent codes from Part 3
