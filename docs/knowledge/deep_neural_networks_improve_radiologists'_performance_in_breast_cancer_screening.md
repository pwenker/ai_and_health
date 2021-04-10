# Deep Neural Networks Improve Radiologists' Performance in Breast Cancer Screening


## Artificial Intelligence


### Health


#### Breast Cancer

### Q: What are the contributions of the paper?

**Answer**: 1) 

-   Primarily, the authors train and evaluate a set of strong neural
    networks on a mammography dataset, with biopsy-proven labels, that
    is of a massive size by the standards of medical image analysis, let
    alone breast cancer screening. 
-   They use two complimentary types of labels: breast-level labels
    indicating whether there is a benign or malignant finding in each
    breast, and pixel-level labels indicating the location of biopsied
    malignant and benign findings. 
-   To quantify the value of pixel-level labels, they compare a model
    using only breast-level labels against a model using both
    breast-level and pixel-level labels. 
-   The best model, trained on both breast-level and pixel-level labels,
    achieves an AUC of 0.895 in identifying malignant cases and 0.756 in
    identifying benign cases on a non-enriched test set reflecting the
    screening population.

2) 

-   In the reader study, the authors compared their best model to that
    of radiologists and found their model to be as accurate as
    radiologists both in terms of area under ROC curve (AUC) and area
    under precision-recall curve (PRAUC). 
-    They also found that a hybrid model, taking the average of the
    probabilities of malignancy predicted by a radiologist and by their
    neural network, yields more accurate predictions than either of the
    two separately. 
-    This suggests that the network and radiologists learned different
    aspects of the task and that their model could be effective as a
    tool providing radiologists a second reader.

3) 

-   Finally, the authors have made the code and weights of their best
    models available at
    https://github.com/nyukat/breast\_cancer\_classifier. 
-   With this contribution, research groups that are working on
    improving screening mammography, which may not have access to a
    large training dataset like theirs, will be able to directly use the
    model in their research or to use their pretrained weights as an
    initialization to train models with less data. 
-   By making the models public, the authors invite other groups to
    validate the results and test the robustness to shifts in the data
    distribution.


### Q: Provide the authors\' problem definition for cancer classification.

**Answer**:

-   For each breast, they assign two binary labels: the absence/presence
    of malignant findings in a breast, and the absence/presence of
    benign findings in a breast.
-   With left and right breasts, each exam has a total of four binary
    labels.
-   The goal of the authors is to produce four predictions corresponding
    to the four labels for each exam.
-   As input, they take four high-resolution images corresponding to the
    four standard screening mammography views.

***Example***:

<div>

\

</div>

<div>

\

</div>

![](images/paste-215da2d28c6e1e2647fbeffd7ff62e92a55cea99.jpg)

<div>

\

</div>

***Remarks***: The authors crop each image to a fixed size of 2677 ×
1942 pixels for CC views and 2974 × 1748 pixels for MLO views.


### Q: Provide the model architecture used for cancer classification.

**Answer**:

-   The authors trained a deep multi-view CNN of architecture shown in
    the figure below (inspired by \"High-resolution breast cancer
    screening with multi-view deep convolutional neural networks\",
    arXiv:1703.07047).
-   The overall network consists of two core modules: (i) four
    view-specific columns, each based on the ResNet architecture that
    outputs a fixed-dimension hidden representation for each mammography
    view, and (ii) two fully connected layers to map from the computed
    hidden representations to the output predictions.
-   The authors used four ResNet-22 columns to compute a 256-dimension
    hidden representation vector of each view.
-   The columns applied to L-CC/R-CC views share their weights. The
    columns applied to L-MLO/R-MLO views share their weights, too.
-   The authors concatenate the L-CC and R-CC representations into a
    512-dimension vector, and apply two fully connected layers to
    generate predictions for the four outputs. They do the same for the
    L-MLO and R-MLO views.
-   They average the probabilities predicted by the CC and MLO branches
    of the model to obtain their final predictions.

***Example***:

<div>

\

</div>

<div>

\

</div>

![](images/paste-82d1db83f23d2931a99144dcb83f9058a618d500.jpg)

<div>

\

</div>

***Remarks***: ResNet-22 refers to our version of a 22-layer ResNet,
with additional modifications such as a larger kernel in the first
convolutional layer.


### Q: What is the patch-level model and why do the authors introduce it?

**Answer**:

-   The high resolution of the images and the limited memory of modern
    GPUs constrain the authors to use relatively shallow ResNets within
    their model when using full-resolution images as inputs.
-   To further take advantage of the fine-grained detail in mammograms,
    they trained an auxiliary model to classify 256 × 256-pixel patches
    of mammograms, predicting two labels: the presence or absence of
    malignant and benign findings in a given patch.
-   The labels for these patches are produced based on the pixel-level
    segmentations of the corresponding mammograms produced by
    clinicians.
-   This approach allows to use a very deep auxiliary network at the
    patch level, as this network does not have to process the entire
    high-resolution image at once.
-   Adding the heatmaps produced by the patch-level classifier as
    additional input channels allows the main classifier to get the
    benefit from pixel-level labels, while the heavy computation
    necessary to produce the pixel-level predictions does not need to be
    repeated each time an example is used for learning.

***Remarks***: The authors refer to this model as a *patch-level model*,
in contrast to the *breast-level model* which operates on images of the
whole breast.\


### Q: How did the authors evaluate their models?

**Answer**:

-   They evaluated their models primarily in terms of AUC (area under
    the ROC curve) for malignant/not malignant and benign/not benign
    classification tasks on the breast level.
-   The model and readers' responses on the subset for reader study are
    evaluated in terms of AUC as well as precision-recall AUC (PRAUC),
    which are commonly used metrics in evaluation of radiologists'
    performance.

***Remarks***:

-   ROC and PRAUC capture diferent aspects of performance of a
    predictive model.
-   The ROC curve summarizes the tradeof between the true positive rate
    and false positive rate for a model using diferent probability
    thresholds.
-   The precision-recall curve summarizes the trade-of between the true
    positive rate (recall) and the positive predictive value (precision)
    for a model using diferent probability thresholds.


