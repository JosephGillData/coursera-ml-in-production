# Machine Learning in Production

Labs and exercises from the Coursera **Machine Learning Engineering for Production (MLOps)** specialization. This repo covers the full ML lifecycle—from training image classifiers to deploying them with FastAPI, Docker, and AWS.

## What's Inside

| Week | Topic | What You'll Learn |
|------|-------|-------------------|
| **Week 1** | Deployment | Build a FastAPI object-detection server, containerize with Docker, deploy to AWS Elastic Beanstalk |
| **Week 2** | Modeling | Train a CNN image classifier (birds/cats/dogs), handle class imbalance, apply data augmentation |

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

## Model Architecture

The image classifier uses a CNN with the following structure:

```
Input (150x150x3)
    ↓
Conv2D (32) → MaxPool → Conv2D (64) → MaxPool
    ↓
Conv2D (64) → MaxPool → Conv2D (128) → MaxPool
    ↓
Flatten → Dense (512) → Dense (3, softmax)
```

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
