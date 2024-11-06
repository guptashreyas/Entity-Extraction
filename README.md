# Entity-Extraction
Project Overview

This project uses a BERT-based model that incorporates both textual information (transcript field) and spatial data (bounding box coordinates). The aim is to improve entity extraction from structured documents that require both contextual and positional understanding.
Key Components

    Data Preprocessing: Tokenization, bounding box normalization, and data balancing.
    Model Architecture: A custom model using BERT embeddings combined with bounding box coordinates.
    Training: Model training with balanced data, including undersampling of OTHER class and oversampling of rare entities.
    Evaluation: Evaluation of model performance on precision, recall, and F1-score.

Entities Extracted

    employerName
    employerAddressStreet_name
    employerAddressCity
    employerAddressState
    employerAddressZip
    einEmployerIdentificationNumber
    employeeName
    ssnOfEmployee
    box1WagesTipsAndOtherCompensations
    box2FederalIncomeTaxWithheld
    box3SocialSecurityWages
    box4SocialSecurityTaxWithheld
    box16StateWagesTips
    box17StateIncomeTax
    taxYear

Evaluation

To evaluate model performance:

    Run the eval.py script, specifying paths for the true labels (val_w_ann) and predicted labels (output_predictions):

python src/eval.py

This outputs precision, recall, and F1-score metrics for each entity and saves results to eval_metrics.tsv.
Results

    Balanced Data: Improved recall and precision for rare classes due to data balancing.
    Custom Model: Combined BERT embeddings and bounding box coordinates to leverage spatial information.

Future Improvements

    Enhance Model Architecture: Experiment with CRF layers or alternative document models (e.g., LayoutLM).
    Hyperparameter Tuning: Fine-tune model parameters to optimize performance further.
    Advanced Augmentation: Use synthetic data for underrepresented entities.
