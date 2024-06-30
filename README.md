# Final Team Project: Music Genre and Composer Classification Using Deep Learning

### Introduction

Music is a ubiquitous art form with a rich history. Different composers have imbued their work with unique styles, making identifying the creator of a piece challenging for novices. This project leverages deep learning to accurately identify the composer of a given musical score.

### Objective

The primary objective is developing a deep learning model to predict the composer of a musical score. We will utilize two techniques:

- Long Short-Term Memory (LSTM)
- Convolutional Neural Network (CNN)

### Project Timeline

- **Module 2 (End of Week 2):** Team formation (2-3 members). Utilize Canvas, USD Email, or Slack.
- **Module 4 (End of Week 4):** Team representative submits "Team Project Status Update Form."
- **Module 7 (End of Week 7):** Final project deliverables due. **No extensions will be granted.**
    - Project Report (PDF)
    - Project Notebook (.ipynb exported as PDF or HTML)

### Dataset

The project utilizes a [Kaggle dataset](https://www.kaggle.com/datasets/blanderbuss/midi-classic-music) of MIDI files from classical composers.  Focus will be on:

1. Bach
2. Beethoven
3. Chopin
4. Mozart

### Methodology

1. **Data Collection:** Dataset provided.
2. **Data Pre-processing:**  Convert scores to MIDI format and apply data augmentation.
3. **Feature Extraction:**  Extract features like notes, chords, and tempo using music analysis tools.
4. **Model Building:** Develop LSTM and CNN models for composer classification.
5. **Model Training:** Train models using pre-processed and feature-extracted data.
6. **Model Evaluation:** Evaluate performance using accuracy, precision, and recall metrics.
7. **Model Optimization:** Fine-tune hyperparameters for optimal performance.

### Deliverables

1. **Project Report (PDF):** Comprehensive documentation in APA 7 style ([Sample Professional Paper](link_to_sample)).
    - File Naming: `DeliverableName-TeamNumber.pdf` (e.g., `Project_Report-Team1.pdf`)
    - Include:
        - Methodology
        - Data pre-processing steps
        - Feature extraction techniques
        - Model architecture
        - Training process
        - Reference list with citations
        - Concluding section with findings and future improvements
2. **Project Notebook (PDF or HTML):** Jupyter Notebook containing the complete project code.
    - Data pre-processing
    - Feature extraction
    - Model building
    - Training
    - Evaluation
    - Additional analysis/visualizations

### Conclusion

This project aims to accurately predict composers of musical scores using LSTM and CNN models. The final model can benefit musicians, enthusiasts, and listeners alike.

### Power Usage

- Utilize Google Colab GPU/TPU for increased computational power.
- Consider subscribing to [Google Colab Pro+](https://colab.research.google.com/signup) if needed.

**Note:** Team member grades may vary based on individual contribution levels.

This assignment uses **Turnitin** for plagiarism detection. Review your work using the **Draft Coach** extension in Google Docs before submission.

### Rubric

#### Final Team Project Scoring Rubric

| Criteria | Ratings | Pts |
|---|---|---|
| **Project Report (25%)** | Meets or Exceeds Expectations: Report thoroughly describes methodology, data preprocessing, feature extraction, model architecture, and training process for reproducibility. | 75 pts |
|  | Approaches Expectations: Report generally describes the above, but needs minor revisions. | 61.5 pts |
|  | Below Expectations: Report minimally describes the above, requiring major revisions. | 52.5 pts |
|  | Inadequate Attempt: Report misses one or more key elements. | 0 pts |
|  | Non-Performance | 0 pts |
| **Project Notebook (65%)** | Meets or Exceeds Expectations: High-quality notebook with complete code, including data preprocessing, feature extraction, model building, training, evaluation, and additional analysis. | 175.5 pts |
|  | Approaches Expectations: Notebook contains all elements but needs minor revisions. | 159.9 pts |
|  | Below Expectations: Notebook contains all elements but needs major revisions. | 136.5 pts |
|  | Inadequate Attempt: Notebook missing one or more key elements. | 0 pts |
|  | Non-Performance | 0 pts |
| **References and Citations (5%)** | Meets or Exceeds Expectations: Complete reference list with proper APA citations. | 13.5 pts |
|  | Approaches Expectations: Reference list needs minor APA formatting revisions. | 12.3 pts |
|  | Below Expectations: Reference list needs major APA formatting revisions. | 10.5 pts |
|  | Inadequate Attempt: Incomplete or missing reference list. | 0 pts |
|  | Non-Performance | 0 pts |
| **Conclusion (5%)** | Meets or Exceeds Expectations: Thorough conclusion summarizing the project, highlighting key findings, and suggesting future improvements. | 13.5 pts |
|  | Approaches Expectations: Adequate conclusion, but could benefit from further elaboration. | 12.3 pts |
|  | Below Expectations: Vague conclusion, lacking key elements. | 10.5 pts |
|  | Inadequate Attempt: Conclusion missing one or more key elements. | 0 pts |
|  | Non-Performance | 0 pts |
| **Total Points:** | | **300** |
