# Documentation Overview for TSP Edge Classification Benchmark

## 01_benchmark_installation.md
This document provides instructions for setting up the project environment.

Key points for engineers:
- Conda environment setup for both CPU and GPU
- Installation of required dependencies
- CUDA setup for GPU users (specifically CUDA 10.2)

Engineers should follow these instructions to ensure a consistent development environment across the team.

## 02_download_datasets.md
This file explains how to download and prepare the TSP dataset.

Key points for engineers:
- Location of the TSP dataset files
- Instructions for downloading using the provided script
- Brief explanation of the dataset's structure and purpose

Engineers working on data preprocessing or adding new datasets should refer to this document as a template.

## 03_run_codes.md
This document outlines how to run experiments using the benchmark.

Key points for engineers:
- Instructions for running experiments via terminal or Jupyter notebook
- Explanation of output directory structure
- Guide to using TensorBoard for visualizing results
- Instructions for reproducing results and generating statistics

This is crucial for engineers conducting experiments or analyzing results.

## 04_add_dataset.md
While currently focused on TSP, this document provides a guide for adding new datasets to the benchmark.

Key points for engineers:
- Structure of the `data/` directory
- Steps to prepare and save a new dataset in DGL format
- How to integrate a new dataset into the existing data loading pipeline
- Explanation of dataset splitting mechanisms

Engineers looking to extend the benchmark to new problems should follow this guide.

## 05_add_mpgcn.md
This document explains how to add a new Message Passing Graph Convolutional Network (MP-GCN) to the project.

Key points for engineers:
- Structure of graph layers and how to implement new ones
- How to create a new graph network class
- Integration of new models into the existing framework
- Modification of training/testing loops if necessary
- Configuration and execution of experiments with new models

This is essential for engineers developing new MP-GCN architectures or modifying existing ones.

## 06_add_wlgnn.md
Similar to 05, but focused on adding Weisfeiler-Lehman type Graph Neural Networks (WL-GNNs).

Key points for engineers:
- Differences in implementation between MP-GCNs and WL-GNNs
- How to handle dense tensor operations in WL-GNNs
- Modifications needed in training loops for WL-GNNs
- Considerations for memory usage in WL-GNNs

Engineers working on more advanced GNN architectures, particularly those dealing with higher-order graph structures, should refer to this document.

# Summary for Engineers

These documentation files provide a comprehensive guide to:
1. Setting up the project environment
2. Obtaining and preparing data
3. Running experiments and analyzing results
4. Extending the benchmark with new datasets
5. Implementing and integrating new GNN architectures (both MP-GCNs and WL-GNNs)

Engineers should use these documents as reference when working on different aspects of the project. They provide a standardized approach to development, ensuring consistency across the project and facilitating collaboration among team members.

When making significant changes or additions to the project, engineers should also update the relevant documentation to keep it current and useful for the entire team.