---
title: "Virtual Staining"
excerpt: "Label-free cell image virtual staining <br/><img src='/images/staining/staining.png'>"
collection: portfolio
---

## Virtual Staining of Subcellular Structures

Fluorescent labeling is the most common method for visualizing subcellular structures in biomedicine, but traditional fluorescent staining has limitations such as damage to cells, tedious operation process, limited staining channels, and fluorescence quenching, which makes it difficult to observe subcellular structures, especially in application scenarios where cell viability needs to be guaranteed. To this end, a deep learning based virtual staining scheme was proposed to establish the correspondence between the bright-field images and the fluorescence images of subcellular structures. And then, the scheme was implemented to predict the fluorescent images of subcellular structures using bright-field images as input.

Firstly, 12 subcellular structures were implemented to virtual staining using the conventional benchmark 3D-UNet model, but an overfitting phenomenon was found on small-scale data sets. To solve this problem, an improved three-dimensional Densely connected U-Net (3D-DUNet) model was proposed and validated on 12 subcellular structures. The virtual staining performance of the proposed 3D-DUNet model exceeds the 3D-UNet model on most subcellular structures. Moreover, the model complexity was reduced by 25% and the number of model parameters was reduced by 95%.

Based on the 3D-DUNet, the three-dimensional Hybrid Attention Dense connected U-Net (3D-HA-DUNet) model was proposed to further improve the model performance, which used the 3D-DUNet combined with the spatial attention mechanism and the channel attention mechanism. The 3D-HA-DUNet model had a 0.5 percentage point improvement in Pearson product-moment Correlation Coefficient (PCCs) compared to the 3D-DUNet model. What's more, a three-dimensional Self Attention Densely connected U-Net (3D-SA-DUNet) model was proposed, which had a global receptive field. In the 3D-DUNet model, an implicit position encoding was innovatively suggested to achieve the prediction of input images at different scales, which solved the problem of the limitition of input images in traditional position encoding. The 3D-DUNet model achieved higher quality of virtual staining with multiple channels on a variety of subcellular structures and enhanced a 1 percentage point improvement in PCCs compared to the 3D-DUNet model, including nucleoli (PCCs=0.88), nuclear envelope (PCCs=0.85), microtubules (PCCs=0.77), actin filaments (PCCs=0.76), endoplasmic reticulum (PCCs=0.74), mitochondria (PCCs=0.72), cell membrane (PCCs= 0.68) and DNA (PCCs=0.63).

To explore the effect of virtual staining in real application scenarios, we extended the virtual staining task from cell lines to more complex human lung cancer cells. A database of paired bright-field images and cell nuclei fluorescence images was constructed by tissue digestion, cell staining, and confocal microscopic imaging of lesion tissue samples from 6 patients with non-small cell lung cancer. The virtual staining of lung cancer nuclei (PCCs=0.77) was achieved for the first time on the submited database using the proposed 3D-SA-DUNet, which could be used to continuously observe the proliferation of cancer cells in drug sensitivity tests.

The implemented virtual staining scheme has many potential applications in biomedicine. In some scenarios where the accuracy of fluorescence staining is generally required, virtual staining can be an efficient alternative to fluorescence staining. Besides, in some scenarios where fluorescence staining is difficult, virtual staining is still feasible, such as dynamic observation of living cells and synergistic analysis of multiple subcellular structures. In addition, the feasibility and potential of virtual staining of lung cancer nuclei in complex human cells were demonstrated, which provided a theoretical basis and practical reference for the application of virtual staining technology to cancer diagnosis, typing, vitro culture, drug screening, enhanced microscopy and other scenarios where fluorescence staining is used.

<img src='/images/staining/stain_metrics.png' alt="models metrics">
<div style="text-align: center;"><figcaption>Performance comparison of different models</figcaption></div>
<br>

<img src='/images/staining/stain_models.png' alt="models metrics">
<div style="text-align: center;"><figcaption>Comparison of model parameters and computation</figcaption></div>
