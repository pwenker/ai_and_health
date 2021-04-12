# A Review of Challenges and Opportunities in Machine Learning for Health


## Artificial Intelligence


### Health


#### Overview

### Q: According to the authors, which three factors should be considered carefully in the design and evaluation of machine learning projects?

**Answer**:  1. Causality,  2. Missingness, and  3. Outcome definition.


### Q: Describe the authors\' \"Google Flue Trends\"-example about \"Internal Validity - Shift over time\" (Non-stationarity in learning and deployment)

**Answer**:

-   In a notable example of concept drift, Google Flu Trends
    persistently overestimated flu due to shifts in search behaviors.
-   The initial model was a great success, leveraging Google search data
    to predict flu incidence.
-   However, without update the model began to overestimate flu
    incidence in subsequent years as user search behaviors had shifted.
-   While the drift was unintentional, the example motivates the need
    for models that continuously update.


### Q: Provide the authors\' example of the Simpson\'s paradox (asthmatic patients admitted to the hospital for pneumonia).

**Answer**:

-   In prior work, researchers found that asthmatic patients who were
    admitted to the hospital for pneumonia were more aggressively
    treated for the infection, lowering the subpopulation mortality
    rate. Hence, a model that predicts death from asthma will learn that
    asthma is protective.
-   If, however, an additional variable to account for the level of care
    is included, the model may instead find that having asthma increases
    the risk of death.

***Remarks***:

-   This example demonstrates that causal models are not only useful to
    evaluate treatments, but can also help to build reliable predictive
    models that do not make harmful predictions using relationships
    caused by treatment policies in the training data.
-   To account for these challenges, strong assumptions must be made
    that cannot be statistically checked or validated; i.e., gathering
    more data will not help.


### Q: According to the authors, which are the three key factors to consider with outcome definitions?

**Answer**:

1.  Creating reliable outcomes,
2.  Understanding the relevance of an outcome clinically, and
3.  The subtlety of label leakage.


### Q: Describe the challenge of \"label leakage\".

**Answer**:

-   The information collected in an individual's hospital encounter is
    tightly coupled across time, and this can result in information
    about the targeted task outcome leaking back into features.
-   While exploiting such relationships between features and targets is
    a goal of learning, information leakage can render a prediction
    meaningless.

***Example***:

-   Consider predicting mortality of hospital patients using all
    available data up until their time of death.
-   Such a task could lead to a pathological prediction rule---"if the
    ventilator is turned off in the preceding hour, predict death."
-   This commonly happens when patients and their families decide to
    withdraw care at a terminal stage of illness.
-   A machine learning algorithm trained naively on this signal would
    have high predictive performance by nearly any metric, yet
    absolutely no clinical utility.


### Q: Provide the authors\' argument of \"Moving from interpretation to justification\".

**Answer**:

-   In other domains, many forms of interpretability rely on human
    expertise, e.g., a model may highlight a single sentence from a user
    review ("The coffee is wonderful.") as the rationale for a review
    prediction.
-   Clinicians are unlikely to have a similar contextual framework, and
    it is unlikely to be obvious what a particular pattern of lab
    measurements that maximally activates a model means, biologically or
    clinically.
-   The authors argue that models should instead provide
    "justifiability"; beyond *explaining* a specific prediction, models
    should strive towards *justifying* the predictive path itself.

***Example***:

-   For example, recent work has proposed that locally-interpretable
    results can be presented for each individual prediction.
-   Another possibility is learning influence functions to trace a
    model's prediction through the learning algorithm and back to its
    training data, thereby identifying training points most responsible
    for a given prediction.

***Remarks***: Outside of reassuring end users, justifying a machine
learning algorithm's decision is also important for security concerns,
as medicine may be uniquely vulnerable to "adversarial attacks".\


### Q: Describe the concept of *precision medicine* for early individualized treatment.

**Answer**:

-   Precision medicine seeks to individualize the treatment of each
    patient
-   This is particularly important for syndromes---conditions defined by
    a collection of symptoms whose causes are unknown.

***Example***:

-   For instance, acute kidney injury (AKI) is defined by a collection
    of symptoms characterizing kidney failure, not an underlying cause.
-   Two individuals may have developed AKI for different reasons because
    there are many reasons that kidneys can fail.
-   More measurements of the two individuals could reveal the difference
    in cause, which may in turn suggest alternative treatment
    strategies.
-   By personalizing over time, one can learn individual-specific
    treatment effects that address the cause of the syndrome in a
    particular individual.
-   This relates to the ideas from "N=1" crossover studies in
    experimental design.
-   Personalized treatment is enabled by growing repositories of
    longitudinal data, where long-term progressions of an individual's
    health are available.


### Q: What is an electronic health record (EHR)?

**Answer**: An electronic health record (EHR) is the systematized
collection of patient and population health information electronically
stored in a digital format. \
***Remarks***:

-   EHRs may include a range of data, including demographics, medical
    history, medication and allergies, immunization status, laboratory
    test results, radiology images, vital signs, personal statistics
    like age and weight, and billing information.
-   Source: <https://en.wikipedia.org/wiki/Electronic_health_record#cite_note-1>


### Q: Provide the authors\' example (the measuring of lactate levels) of the three missing data mechanisms MCAR, MAR, MNAR .

**Answer**: For example, lab measurements are typically ordered as part
of a diagnostic work-up, meaning that the presence of a datapoint
conveys information about the patient's state. Consider a hospital where
clinical staff measures patient lactate level. 

1.  If a power outage led to a set of lactate levels being lost, the
    data are MCAR. 
2.  If nurses are less likely to measure lactate levels in patients with
    traumatic injury, and we record whether patients were admitted with
    trauma, the data are MAR. 
3.  However, if nurses are less likely to measure lactate levels when
    believed to be already, then the lactate measures themselves are
    MNAR, and the measurement of the signal itself is meaningful.

***Remarks***: The key feature of missing data is that there may be
information conveyed by the absence of an observation, and ignoring this
dependence may lead to models that make incorrect, and even harmful,
predictions.


### Q: Provide some of the examples of ensuring interpretability of machine learning models.

**Answer**: There are many possible ways to interpretability, e.g., 

<div>

-   through feature space minimization, 
-   model regularization, 
-   or a preference for particular classes of models that have
    well-known post-hoc analysis methods.

</div>

***Example***:

-   For example, providing a posterior distribution over possible
    decision lists.
-   Such lists can provide a natural way for clinicians to think about
    the relative risks of their patient's condition.


### Q: Which three widely accepted classifications of missing data mechanisms exist?

**Answer**:

1.  The first, **missing completely at random** (**MCAR**), posits a
    fixed probability of missingness. In this case, dropping incomplete
    observations---known as complete case analysis---is commonly used
    (albeit naively), and will lead to unbiased results.
2.  Second, the data may be **missing at random** (**MAR**), where the
    probability of missingness is random conditional on the observed
    variables. In this case, common methods include re-weighting data
    with methods like inverse probability of censoring weighting or
    using multiple imputations to in-fill.
3.  Finally, data may be **missing not at random** (**MNAR**), where the
    probability of missingness depends on the missing variable itself,
    or other missing and unobserved variables.


### Q: Describe the importance of creating reliable outcomes from heterogeneous source data.

**Answer**:

-   Multiple data sources should be considered when creating labels
    because EHRs often lack precise structured labels.
-   Or, in some cases, structured labels may be unreliable.

***Example***:

-   For example, a diagnostic clinical code for pneumonia could mean a
    patient was screened for pneumonia rather than that they actually
    had pneumonia.
-   Machine learning methods to pool different data types and obtain a
    more reliable label is known as phenotyping, and is an important
    subfield of machine learning in healthcare.

***Remarks***: Recent work has emphasized the need to integrate the rich
information available in clinical notes, and building natural language
processing pipelines to extract information from unstructured clinical
text accurately is an active subject of research.\


### Q: Describe the challenge of \"External Validity - Shift over sources\" (Non-stationarity in learning and deployment)

**Answer**:

-   There is also no reason to believe a priori that a model learned
    from one hospital will generalize to a new one.
-   Many factors impact generalizability, including local hospital
    practices, different patient populations, available equipment, and
    even the specific kind of EHR each uses---transitions from one EHR
    to another create non-obvious feature mapping problems.

***Remarks***:

-   This issue will remain until infrastructure to easily test across
    multiple sites becomes prevalent.
-   The absence of such standardization creates opportunities with
    respect to data normalization and the development of models that are
    robust to differences in data collection at different sites.


### Q: Describe the importance of the integration of fragmented records.

**Answer**: Finite resources can also lead to a lack of communication
and coordination, affecting patient care. ***Example***:

-   For example, it can take years to identify domestic abuse survivors
    because any single clinical visit in isolation may be consistent
    with other causes (e.g. an admission for bruising is consistent with
    a spontaneous fall).
-   Only a thorough review of a patient's record will demonstrate the
    pattern of repeated admissions and other indicators (e.g., partners'
    alcohol abuse).
-   While possible without support systems in principle, machine
    learning can be a powerful tool, e.g., identifying domestic abuse up
    to 30 months in advance of the healthcare system.


