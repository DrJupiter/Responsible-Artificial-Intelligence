### Course Overview: Responsible AI

**General Course Objectives**

This course introduces students to ethical challenges in AI and provides tools to understand and address them. Key topics include:

- Paradigms and limitations of machine learning (Epistemology)
- Fairness and bias
- Explainable-AI
- Privacy

Students will engage with current state-of-the-art topics and recent publications from relevant ML conferences and journals. They will also implement prototypes of the presented algorithms and share their observations and results with the class.

**Learning Objectives**

The course aims to enhance knowledge in four major areas of responsible AI:

1. **Understanding AI:** Gain a deep understanding of AI, including common assumptions and responsible AI development practices.
2. **Fairness and Bias:** Learn about the challenges and state-of-the-art solutions for fairness and bias in AI.
3. **Explainable-AI:** Gain hands-on experience with deep neural network interpretations and explainable-AI techniques.
4. **Privacy:** Work with privacy-preserving models and training strategies.

**Content**

The course is divided into four parts:

1. **Ethics and Epistemology of AI:**
   - Ethical considerations in AI
   - Epistemology of machine learning
   - Model-fitting vs. artificial intelligence
   - Bayesian problems and limitations

2. **Fairness in AI:**
   - Review of classical algorithmic fairness algorithms
   - Limitations and potential solutions

3. **Explainable-AI:**
   - Saliency and prototype-based methods
   - Use cases and validation of explainable-AI methods

4. **Privacy in AI:**
   - Differential privacy
   - Federated learning

This comprehensive approach ensures students build a robust understanding of responsible AI practices, preparing them to tackle ethical challenges in AI development and deployment.


### Project 1: Algorithmic Fairness in Predicting Juvenile Recidivism

**Objective:**
This project focuses on addressing bias in predicting juvenile recidivism using the "Recidivism in juvenile justice" dataset. It evaluates fairness using three metrics—Independence, Separation, and Sufficiency—and implements a bias mitigation technique.

**Data Description:**
The dataset consists of 4652 individuals aged 14-17 under a criminal program. It includes both continuous and discrete features, with sensitive categories such as gender, origin, and age. The data distribution is unbalanced, which introduces potential bias.

**Model Choices:**
A simple neural network with three linear layers and ReLU activation functions was used, finalized with a Sigmoid function to predict the likelihood of recidivism. The data was split into training, validation, and test sets (60%, 15%, and 25%, respectively). The model achieved a validation accuracy of 0.73 and a test accuracy of 0.71.

**Fairness Measure:**
Fairness was evaluated using Independence, Separation, and Sufficiency metrics. The results indicated significant bias across different groups, particularly in gender and origin.

**Bias Mitigation Technique:**
A bias mitigation technique was applied to address sufficiency for the origin category. This involved minimizing the mutual information between the ground truth label and the sensitive group, conditioned on the output of a feature extractor. However, the mitigation approach led to reduced model performance and did not significantly improve fairness.

**Conclusion:**
The project highlighted the presence of bias in the model's predictions, particularly concerning gender and origin. The implemented bias mitigation technique did not yield the desired improvement in fairness, suggesting the need for further analysis and debugging.

**GitHub Repository:** [Responsible-AI-1](https://github.com/DrJupiter/Responsible-Ai-1)

### Project 2: Explainable AI (XAI) - Saliency Maps and Prototype-based Bottleneck Models

**Objective:**
This project explores Explainable AI (XAI) methods to enhance transparency and interpretability in AI systems. It focuses on two XAI techniques—saliency maps and prototype-based bottleneck models—and discusses their quantitative validation.

**Introduction:**
Explainable AI (XAI) addresses issues of transparency and trust in AI by providing insights into the decision-making processes of AI systems. This project examines XAI using the CUB dataset, focusing on three bird images to evaluate and compare different XAI methods.

**Methods:**

1. **Saliency Maps:**
   - **Model Used:** Pretrained VGG16 convolutional network.
   - **Approach:** Standard gradient-based saliency maps to highlight important regions in images.
   - **Results:** Saliency maps emphasized the birds, particularly their heads, indicating relevant features for classification.

2. **Prototype-based Bottleneck Models (Proto-PNet):**
   - **Model Used:** Proto-PNet based on VGG19, trained on the CUB dataset.
   - **Approach:** Generates prototypes to identify meaningful features such as bird tails, heads, and colors.
   - **Results:** Prototypes successfully highlighted distinguishable features, though some irrelevant features like background were also identified.

**Comparison of Methods:**
- **Saliency Maps:** Provide directionality for increasing class likelihood, visualized as highlighted image regions.
- **Proto-PNet:** Identifies important regions through similarity to learned prototypes, offering more interpretable features like bird parts.

**Quantitative Validation:**
- **Saliency Maps Validation:** Compared consistency using average FID scores across classes, finding gradient saliency maps more consistent than Gaussian saliency maps.
- **Proto-PNet Validation:** Evaluated patches from prototypes on saliency maps, assessing agreement between model activations and identified patches.

**Conclusion:**
Both methods offer valuable insights into AI decision-making, with Proto-PNet providing more humanly interpretable features. The quantitative validation strategies help in assessing the consistency and reliability of the explanations provided by these XAI methods.

