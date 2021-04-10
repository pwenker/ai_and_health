# Breast Cancer Detection

- Breast cancer screening is the medical screening of asymptomatic, apparently healthy women for breast cancer in an attempt to achieve an earlier diagnosis. 
- The assumption is that early detection will improve outcomes. 
- A number of screening tests have been employed, including clinical and self breast exams, mammography, genetic screening, ultrasound, and magnetic resonance imaging.
(source: [wikipedia/breast_cancer_screening](https://en.wikipedia.org/wiki/Breast_cancer_screening))



## Breast cancer incidence and mortality before and after implementation of the German mammography screening program (2020-08-01) :book:
(_Alexander Katalinic, Nora Eisemann, Klaus Kraywinkel, Maria R. Noftz, Joachim Hübner_)

**Abstract**:

- Effective population-based mammography screening should impact breast cancer (BC) incidence, age and stage-specific incidence and BC mortality. 
- The authors aim to investigate such effects in a time period of 10 years after implementation of the German mammography screening program. 
- Data on 323,719 breast cancer patients from 2003 to 2014 for defined regions covering a population of 30 million inhabitants and official mortality data from 1998 to 2016 for almost the whole of Germany were used. 
- The authors compared incidence and mortality rates for the prescreening time period (2003/2004) and the latest available data (2013/2014 and 2015/2016, respectively) and performed trend analyses using joinpoint regression models. 
- In the screening exposed age groups (50-59 and 60-69 years), BC incidence showed a typical prevalence peak with the introduction of the mammography screening, mainly driven by an increase of early-stage BC. 
- For Stage III and IV BC incidence in 2013/2014 was 24.2 and 23.0% (age group 50-59 years) and 28.3 and 24.2% (age group 60-69 years) lower than in the prescreening period. 
- From 2003/2004 to 2015/2016 BC mortality decreased by 25.8 and 21.2%, respectively. 
- As corresponding trends in nonexposed age groups were distinctly unfavorable, the reduction of late-stage BC incidence and BC mortality in the screening exposed age groups in Germany is most likely to be attributed to the introduction of the national mammography screening program. 
- These positive effects are bought at the cost of a moderate occurrence of overdiagnosis, especially by a sharp increase of in situ cancers.



## Deep learning in breast radiology: current progress and future directions (2021-01-15) :book:
(_William C. Ou, Dogan Polat, Basak E. Dogan_)

**Abstract**:

- This review provides an overview of current applications of deep learning methods within breast radiology. 
- The diagnostic capabilities of deep learning in breast radiology continue to improve, giving rise to the prospect that these methods may be integrated not only into detection and classification of breast lesions, but also into areas such as risk estimation and prediction of tumor responses to therapy.
- Remaining challenges include limited availability of high-quality data with expert annotations and ground truth determinations, the need for further validation of initial results, and unresolved medicolegal considerations. 

**Key Points**: 
- Deep learning (DL) continues to push the boundaries of what can be accomplished by artificial intelligence (AI) in breast imaging with distinct advantages over conventional computer-aided detection.
- DL-based AI has the potential to augment the capabilities of breast radiologists by improving diagnostic accuracy, increasing efficiency, and supporting clinical decision-making through prediction of prognosis and therapeutic response. 
- Remaining challenges to DL implementation include a paucity of prospective data on DL utilization and yet unresolved medicolegal questions regarding increasing AI utilization.



## Deep Neural Networks Improve Radiologists’ Performance in Breast Cancer Screening (2019-03-19) :book:
(_Nan Wu, Jason Phang, Jungkyu Park, Yiqiu Shen, Zhe Huang, Masha Zorin, Stanisław Jastrzębski, Thibault Févry, Joe Katsnelson, Eric Kim, Stacey Wolfson, Ujas Parikh, Sushma Gaddam, Leng Leng Young Lin, Kara Ho, Joshua D. Weinstein, Beatriu Reig, Yiming Gao, Hildegard Toth, Kristine Pysarenko, Alana Lewin, Jiyon Lee, Krystal Airola, Eralda Mema, Stephanie Chung, Esther Hwang, Naziya Samreen, S. Gene Kim, Laura Heacock, Linda Moy, Kyunghyun Cho, Krzysztof J. Geras_)

**Link**: http://arxiv.org/abs/1903.08297

**Abstract**:

- The authors present a deep convolutional neural network for breast cancer screening exam classification, trained and evaluated on over 200,000 exams (over 1,000,000 images). 
- Their network achieves an AUC of 0.895 in predicting whether there is a cancer in the breast, when tested on the screening population. 
- The authors attribute the high accuracy of their model to a two-stage training procedure, which allows them to use a very high-capacity patch-level network to learn from pixel-level labels alongside a network learning from macroscopic breast-level labels. 
- To validate their model, they conducted a reader study with 14 readers, each reading 720 screening mammogram exams, and found their model to be as accurate as experienced radiologists when presented with the same data.
- Finally, the authors show that a hybrid model, averaging probability of malignancy predicted by a radiologist with a prediction of their neural network, is more accurate than either of the two separately. 
- To better understand their results, the authors conduct a thorough analysis of the network's performance on different subpopulations of the screening population, model design, training procedure, errors, and properties of its internal representations.



## International evaluation of an AI system for breast cancer screening (2020) :book:
(_S. McKinney, M. Sieniek, Varun Godbole, J. Godwin, N. Antropova, H. Ashrafian, T. Back, Mary Chesus, Greg C. Corrado, A. Darzi, Mozziyar Etemadi, Florencia Garcia-Vicente, F. J. Gilbert, M. Halling-Brown, Demis Hassabis, S. Jansen, A. Karthikesalingam, Christopher J. Kelly, Dominic King, J. R. Ledsam, D. Melnick, H. Mostofi, Lily Peng, J. Reicher, B. Romera-Paredes, R. Sidebottom, Mustafa Suleyman, Daniel Tse, K. C. Young, J. Fauw, S. Shetty_)

**Abstract**:

- Screening mammography aims to identify breast cancer before symptoms appear,
enabling earlier therapy for more treatable disease
- Despite the existence of screening programmes worldwide, the interpretation of mammograms is affected by high rates of false positives and false negatives 
- Here, the authors present an artificial intelligence (AI) system that is capable of surpassing human experts in breast cancer prediction. 
- To assess its performance in the clinical setting, the authors curated a large representative dataset from the UK and a large enriched dataset from the USA. 
- The authors show an absolute reduction of 5.7% and 1.2% (USA and UK) in false positives and 9.4% and 2.7% in false negatives. 
- They provide evidence of the ability of the system to generalize from the UK to the USA. 
- In an independent study of six radiologists, the AI system outperformed all of the human readers: the area under the receiver operating characteristic curve (AUC-ROC) for the AI system was greater than the AUC-ROC for the average radiologist by an absolute margin of 11.5%. 
- The authors ran a simulation in which the AI system participated in the double-reading process that is used in the UK, and found that the AI system maintained non-inferior performance and reduced the workload of the second reader by 88%. 
- This robust assessment of the AI system paves the way for clinical trials to improve the accuracy and efficiency of breast cancer screening. 
- An artificial intelligence (AI) system performs as well as or better than radiologists at detecting breast cancer from mammograms, and using a combination of AI and human inputs could help to improve screening efficiency.



## nyukat/breast_cancer_classifier :computer:

**Link**: https://github.com/nyukat/breast_cancer_classifier

**Abstract**:

- This is an implementation of the model used for breast cancer classification as described in the paper "Deep Neural Networks Improve Radiologists' Performance in Breast Cancer Screening". 
- The implementation allows users to get breast cancer predictions by applying one of their pretrained models: a model which takes images as input (image-only) and a model which takes images and heatmaps as input (image-and-heatmaps).



## Papers with Code - Breast Cancer Detection :book:

**Link**: https://paperswithcode.com/task/breast-cancer-detection



## Bibliography

<div class="csl-entry">Ou, William C., et al. “Deep Learning in Breast Radiology: Current Progress and Future Directions.” <i>European Radiology</i>, Jan. 2021, doi:10.1007/s00330-020-07640-9.</div>
<div class="csl-entry"><i>PubMed Entry</i>. http://www.ncbi.nlm.nih.gov/pubmed/33449174. Accessed 28 Mar. 2021.</div>
<div class="csl-entry"><i>Submitted Version</i>. https://www.repository.cam.ac.uk/bitstream/1810/299195/1/final_submission_Nature.pdf. Accessed 28 Mar. 2021.</div>
<div class="csl-entry">McKinney, S., et al. “International Evaluation of an AI System for Breast Cancer Screening.” <i>Nature</i>, 2020, doi:10.1038/s41586-019-1799-6.</div>
<div class="csl-entry"><i>Semantic Scholar Link</i>. https://www.semanticscholar.org/paper/International-evaluation-of-an-AI-system-for-breast-McKinney-Sieniek/acb0b04bf282a5a04bd2ca050d8be3dec78a4668. Accessed 28 Mar. 2021.</div>
<div class="csl-entry"><i>Nyukat/Breast_cancer_classifier</i>. 2018. nyukat, 2021, https://github.com/nyukat/breast_cancer_classifier.</div>
<div class="csl-entry">Wu, Nan, et al. “Deep Neural Networks Improve Radiologists’ Performance in Breast Cancer Screening.” <i>ArXiv:1903.08297 [Cs, Stat]</i>, 1, Mar. 2019, http://arxiv.org/abs/1903.08297.</div>
<div class="csl-entry"><i>Full Text</i>. https://onlinelibrary.wiley.com/doi/pdfdirect/10.1002/ijc.32767. Accessed 26 Mar. 2021.</div>
<div class="csl-entry"><i>PubMed Entry</i>. http://www.ncbi.nlm.nih.gov/pubmed/31675126. Accessed 26 Mar. 2021.</div>
<div class="csl-entry">Katalinic, Alexander, et al. “Breast Cancer Incidence and Mortality before and after Implementation of the German Mammography Screening Program.” <i>International Journal of Cancer</i>, vol. 147, no. 3, Aug. 2020, pp. 709–18, doi:10.1002/ijc.32767.</div>
<div class="csl-entry"><i>Papers with Code - Breast Cancer Detection</i>. https://paperswithcode.com/task/breast-cancer-detection. Accessed 26 Mar. 2021.</div>