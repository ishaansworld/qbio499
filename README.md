# qbio499
Course: AI &amp; ML in Biology and Medicine

Below, I have copied the descriptions provided to complete these 3 projects.

## scRNAseq Auto-Encoder

Single-cell RNA-Seq (scRNA-Seq) data is incredibly noisy and sparse, with only a fraction of transcribed RNAs captured in the sequencing due to the difficulty in amplifying such a small signal from a single cell. Specifically, there are many genes expressed in a cell at any given time, and two entirely different scRNA-Seq readings could come from cells with identical expression profiles.

In this assignment, you will explore utilizing autoencoders to identify clusters of cells from the counts data. These clusters could represent varying expression profiles in the same tissue sample, such as the unique profiles that you might see in different phases of the cell cycle or different cell types. counts.npy is a scRNA-seq gene expression matrix with 5000 cells and 1000 genes. Cell represents the normalized log gene expression value of j-th gene in i-th sample. labels.txt is the corresponding cluster these cells belong to. There are a total of 3 clusters.

1. Train an Autoencoder (composed of fully-connected layers) to learn a low-level gene expression representation of the cells from the scRNA-Seq counts. Use and compare different latent embedding sizes of 10 and 50.

2. Report and compare the Mean Squared Error (MSE) between the reconstruction and original data for each latent embedding size. How does the size of the latent space affect the reconstruction MSE?

3. Compare and report the plots of the original data with the plots of the reconstructions. How do the PCA and t-SNE plots of the reconstructions compare with those of the original data? Here we only consider latent embedding size of 10.

4. Compare and report the plots of the original data and the plots of the latent vectors. How do the various embedding sizes change the quality of clustering? Here we only consider latent embedding size of 10.

5. Try to use a non-zero MSE loss function to replace MSE when training your AE model. Compare the reconstruction Mean Squared Error (MSE) with latent embedding size of 10. Then plot the PCA and t-SNE plots of the reconstructions and latent vectors with original data. What
clonclusion can you get?

## Predicting TF Binding Affinity Using DNA Shape Features

Transcription factor (TF) binding to DNA is governed by two main mechanisms: base readout and shape readout. Base readout enables TFs to identify their DNA binding sites based on the DNA's physicochemical patterns, while shape readout allows TFs to recognize binding sites through the 3D structure of the DNA. Before the development of tools such as DNAshape, predicting the 3D structural features of DNA in a high-throughput manner was challenging. In this project, you will utilize the DNAshape tool to explore the significance of DNA shape in TF-DNA binding and assess its impact on the predictive capabilities, analyzing gcPBM data for the transcription factors Max, Mad, and Myc. In this exercise, we will use four major DNA shape features: MGW (minor groove width), ProT (propeller twist), Roll, and HelT (helical twist).

1. Install the Deep DNAshape package to obtain DNA shape features for the input files Max.txt, Mad.txt, and Myc.txt. Generate a feature vector for “1-mer” sequence model, a feature vector for “2-mer” sequence model and a feature vector for “1-mer+shape” model for each of the datasets corresponding to Mad, Max and Myc.

2. Build L2-regularized multiple linear regression (MLR) models for “1-mer”, “2-mer” and “1-mer+shape” features with 10-fold cross validation. Calculate and report the average R2 (coefficient of determination) for each of these three models across the datasets of Mad, Max and Myc.

3. Generate two plots for a comparison of two different models: one comparing the “1mer” vs. “1mer+shape” and another comparing the “2mer” vs. “1mer+shape” model. Briefly discuss what you have learned from the results.

4. Repeat the process outlined in Q1 for ChIP-seq data (ctcf_bound.fasta and ctcf_unbound.fasta) for the CTCF TF from Mus musculus. Build logistic regression models for the “1-mer”, “2-mer” and “1-mer+shape” features, Plot the ROC curves for each model and calculate the AUC score for each curve. Briefly discuss what you have learned from the results.

## Temporal Gene Expression Analysis with LSTMs and FCNNs

Dynamic changes in gene expression, orchestrated by complex internal and external signaling networks, are crucial in determining cellular states and fates. Despite the variability observed at the single-cell level, Raj and Van Oudenaarden (Cell, 2008) highlight that predictable patterns of gene expression emerge over time or across cell populations. In this assignment, you will develop a Long Short-Term Memory (LSTM) network to analyze the temporal dynamics of gene expression data, aiming to capture these temporal dependencies. You will then compare its performance with that of fully connected neural networks (FCNN). This task focuses on the challenge of classifying and predicting gene expression dynamics across various groups of genes.

1. Build a Fully Connected Neural Network (FCNN) for Gene Expression Classification: Begin by loading the dynamic gene expression data from gene_expression_data.csv, which comprises 1000 samples, each featuring 10 genes across 20 time steps with normalized expression levels. Your task is to develop an FCNN that can classify gene expression dynamics into two distinct classes as indicated by the 'outcome' column in the dataset—'1' for upregulation and '0' for downregulation. After loading the dataset, divide it into training and testing sets, maintaining a test size of 20%. Design your FCNN to include two dense layers and embark on the training process for a duration of 30 epochs.

2. Model Performance Evaluation and Analysis: Evaluate your FCNN's performance by examining the training and testing accuracy and loss. Discuss any observed issues with the training or testing results and suggest applicable techniques to address them. Justify your choice of techniques.

3. LSTM Model for Temporal Gene Expression Classification: Shift focus to predicting gene expression dynamics by developing an LSTM model that captures temporal dependencies. Load and preprocess the dataset to match the LSTM's expected input shape (num_samples, num_time_steps, num_genes), basing your reshaping on the provided column names, and keep a test size of 20%. Design the LSTM for binary classification, embarking on a training process for a duration of 30 epochs with the goal of surpassing a test accuracy of 0.8.

4. LSTM Model Evaluation and FCNN Comparison: Post-training, evaluate your LSTM model as you do for the Q2. Provide an analysis of the LSTM's results, comparing its performance against the FCNN. Conclude by discussing the implications of your findings and draw conclusions on the effectiveness of LSTM models in capturing temporal gene expression dynamics versus FCNN.
