# Machine Learning in Production

Labs and exercises from the Coursera **Machine Learning Engineering for Production (MLOps)** specialization. This repo covers the full ML lifecycle—from training image classifiers to deploying them with FastAPI, Docker, and AWS.

## What's Inside

| Week | Topic | Content |
|------|-------|-------------------|
| **1** | Deployment | Build a FastAPI object-detection server, containerize with Docker, deploy to AWS Elastic Beanstalk |
| **2** | Modeling | Train a CNN image classifier (birds/cats/dogs), handle class imbalance, apply data augmentation |
| **3** | Data Labeling | Explore how labeling quality affects model performance, build rule-based automatic labeling strategies |

## Quick Start

### Prerequisites

- Python 3.8+
- Jupyter Notebook, VS Code, or Google Colab
- Docker (for deployment labs)
- AWS account (optional, for cloud deployment)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/coursera-ml-in-production.git
cd coursera-ml-in-production

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install tensorflow numpy pandas seaborn matplotlib scikit-learn fastapi uvicorn python-multipart
```

### Running the Labs

**Modeling Lab (Week 2):**
```bash
jupyter notebook wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb
```

**Deployment Lab (Week 1):**
```bash
# Start the FastAPI server
jupyter notebook wk1_deployment/lab_1/server-coursera.ipynb

# In another terminal, run the client
jupyter notebook wk1_deployment/lab_1/client-coursera.ipynb
```

**Data Labeling Lab (Week 3):**
```bash
jupyter notebook wk3_data/C1W3_Data_Labeling_Ungraded_Lab.ipynb
```

**Docker Deployment:**
```bash
docker build -t ml-server .
docker run -d --name ml-server -p 80:80 ml-server
```

## Project Structure

```
coursera-ml-in-production/
├── wk1_deployment/
│   ├── lab_1/
│   │   ├── server-coursera.ipynb   # FastAPI object detection server
│   │   └── client-coursera.ipynb   # Client that consumes the API
│   └── lab_2/
│       └── home/jovyan/work/
│           ├── docker-deploy.ipynb # Docker containerization tutorial
│           └── cloud-deploy.ipynb  # AWS Elastic Beanstalk deployment
│
├── wk2_modelling/
│   ├── C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb  # Main modeling notebook
│   ├── lab_utils.py                # Helper functions (model creation, plotting)
│   ├── models/                     # Pre-trained model weights
│   └── histories/                  # Saved training histories for plotting
│
├── wk3_data/
│   ├── C1W3_Data_Labeling_Ungraded_Lab.ipynb   # Data labeling notebook
│   ├── data/                       # YouTube spam comment CSVs
│   └── assets/                     # Labeling strategy images
│
└── README.md
```

## Key Features

### Week 1: ML Deployment
- **FastAPI Server**: RESTful API serving an object detection model
- **Docker**: Containerize ML applications for consistent deployments
- **AWS Elastic Beanstalk**: Deploy to production with managed infrastructure

### Week 2: Model Training
- **CNN Architecture**: Custom convolutional neural network for image classification
- **Data Pipeline**: Dataset splitting, preprocessing, and augmentation
- **Handling Imbalance**: Techniques for working with imbalanced datasets
- **Transfer Learning Ready**: Architecture designed for easy extension

### Week 3: Data Labeling
- **Labeling Impact**: Compare model performance across different labeling strategies
- **Performance Baselines**: Establish lower (random) and upper (true labels) bounds
- **Rule-Based Labeling**: Build automatic labeling using domain-specific rules
- **Text Classification**: Naive Bayes classifier with CountVectorizer for spam detection

## Tips

- **No GPU?** Use the pre-trained models in `wk2_modelling/models/` and training histories in `wk2_modelling/histories/`
- **Run cells in order**: Each notebook has setup cells at the top—run these first
- **Docker/Cloud labs**: Follow the notebook cells exactly; they contain step-by-step commands and screenshots

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.68+-green?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Supported-blue?logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Elastic%20Beanstalk-orange?logo=amazon-aws&logoColor=white)

## License

This project contains educational materials from Coursera's MLOps specialization.