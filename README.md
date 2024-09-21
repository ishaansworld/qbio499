# qbio499
AI &amp; ML in Biology and Medicine

Below, I have copied the descriptions provided to complete these projects.

## scRNAseq Auto-Encoder

Single-cell RNA-Seq (scRNA-Seq) data is incredibly noisy and sparse, with only a fraction of transcribed RNAs captured in the sequencing due to the difficulty in amplifying such a small signal from a single cell. Specifically, there are many genes expressed in a cell at any given time, and two entirely different scRNA-Seq readings could come from cells with identical expression profiles.

In this assignment, you will explore utilizing autoencoders to identify clusters of cells from the counts data. These clusters could represent varying expression profiles in the same tissue sample, such as the unique profiles that you might see in different phases of the cell cycle or different cell types. counts.npy is a scRNA-seq gene expression matrix with 5000 cells and 1000 genes. Cell represents the normalized log gene expression value of j-th gene in i-th sample. labels.txt is the corresponding cluster these cells belong to. There are a total of 3 clusters.

1. Train an Autoencoder (composed of fully-connected layers) to learn a low-level gene expression representation of the cells from the scRNA-Seq counts. Use and compare different latent embedding sizes of 10 and 50.

2. Report and compare the Mean Squared Error (MSE) between the reconstruction and original data for each latent embedding size. How does the size of the latent space affect the reconstruction MSE?

3. Compare and report the plots of the original data with the plots of the reconstructions. How do the PCA and t-SNE plots of the reconstructions compare with those of the original data? Here we only consider latent embedding size of 10.

4. Compare and report the plots of the original data and the plots of the latent vectors. How do the various embedding sizes change the quality of clustering? Here we only consider latent embedding size of 10.

5. Try to use a non-zero MSE loss to replace MSE when training your AE model. Compare the reconstruction Mean Squared Error (MSE) with latent embedding size of 10. Then plot the PCA and t-SNE plots of the reconstructions and latent vectors with original data. What
clonclusion can you get?
