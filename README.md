# coursera-ml-in-production

This repository contains course labs for deploying and modeling simple ML apps. See the sections below for what each file/folder does and how to run it.

## Layout
- [wk1_deployment](wk1_deployment) — Deployment labs (FastAPI, Docker, Cloud)
  - [wk1_deployment/lab_1/client-coursera.ipynb](wk1_deployment/lab_1/client-coursera.ipynb) — Notebook client that consumes the FastAPI object-detection server.
  - [wk1_deployment/lab_1/server-coursera.ipynb](wk1_deployment/lab_1/server-coursera.ipynb) — Notebook that implements the FastAPI server used in lab_1.
  - [wk1_deployment/lab_2/home/jovyan/work/docker-deploy.ipynb](wk1_deployment/lab_2/home/jovyan/work/docker-deploy.ipynb) — Docker packaging lab; shows `docker build -t w1_lab .` and `docker run -d --name w1_lab -p 80:80 w1_lab`.
  - [wk1_deployment/lab_2/home/jovyan/work/cloud-deploy.ipynb](wk1_deployment/lab_2/home/jovyan/work/cloud-deploy.ipynb) — AWS Elastic Beanstalk deployment walkthrough.
- [wk2_modelling](wk2_modelling) — Modeling labs (data prep, training, augmentation)
  - [wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb](wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb) — Main lab notebook demonstrating dataset preparation, imbalance, augmentation, training and evaluation.
  - [wk2_modelling/lab_utils.py](wk2_modelling/lab_utils.py) — Helper functions used by the lab. Key symbols:
    - [`lab_utils.move_to_destination`](wk2_modelling/lab_utils.py)
    - [`lab_utils.copy_with_limit`](wk2_modelling/lab_utils.py)
    - [`lab_utils.create_model`](wk2_modelling/lab_utils.py)
    - [`lab_utils.get_training_metrics`](wk2_modelling/lab_utils.py)
    - [`lab_utils.plot_train_eval`](wk2_modelling/lab_utils.py)
    - [`lab_utils.demo_augmentation`](wk2_modelling/lab_utils.py)
  - [wk2_modelling/models](wk2_modelling/models) — pretrained model folders referenced by the notebook.
  - [wk2_modelling/histories](wk2_modelling/histories) — saved training histories (.pkl) used for plotting.

## Requirements
- Python 3.8+ with packages listed in notebooks or environment:
  - Typical: tensorflow, numpy, pandas, seaborn, matplotlib, scikit-learn
- For Docker/cloud labs: Docker CLI and (optionally) an AWS account.

## How to run / open
- Notebooks: open with Jupyter/Colab/VSCode Notebook.
  - Example: open [wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb](wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb) in Jupyter or Colab.
- Python helpers:
  - Import helpers in a notebook or script: `import wk2_modelling.lab_utils as lab_utils` (or `import lab_utils` when running from inside that folder).
  - See [`lab_utils.create_model`](wk2_modelling/lab_utils.py) for the model architecture and compilation.
- Docker deployment (see [docker-deploy.ipynb](wk1_deployment/lab_2/home/jovyan/work/docker-deploy.ipynb)):
  - Build: docker build -t w1_lab .
  - Run: docker run -d --name w1_lab -p 80:80 w1_lab
  - Manage: docker stop w1_lab / docker start w1_lab / docker rm w1_lab
- Cloud deployment (see [cloud-deploy.ipynb](wk1_deployment/lab_2/home/jovyan/work/cloud-deploy.ipynb)):
  - Follow the notebook to package the app zip and deploy using AWS Elastic Beanstalk UI (or CLI).

## Quick file-purpose map
- [wk1_deployment/lab_1/client-coursera.ipynb](wk1_deployment/lab_1/client-coursera.ipynb) — Example client using `requests` to POST images to the server and save/display returned images.
- [wk1_deployment/lab_1/server-coursera.ipynb](wk1_deployment/lab_1/server-coursera.ipynb) — FastAPI server example that serves object detection endpoints.
- [wk1_deployment/lab_2/home/jovyan/work/docker-deploy.ipynb](wk1_deployment/lab_2/home/jovyan/work/docker-deploy.ipynb) — Step-by-step Dockerfile build/run instructions; references `app/main.py` inside the downloadable zip.
- [wk1_deployment/lab_2/home/jovyan/work/cloud-deploy.ipynb](wk1_deployment/lab_2/home/jovyan/work/cloud-deploy.ipynb) — Step-by-step Elastic Beanstalk deployment guide.
- [wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb](wk2_modelling/C1W2_Ungraded_Lab_Birds_Cats_Dogs.ipynb) — End-to-end modeling lab; runs data extraction, splits, training (or loads pretrained models), evaluation, and augmentation experiments.
- [wk2_modelling/lab_utils.py](wk2_modelling/lab_utils.py) — Utility functions used throughout the modeling notebook (see linked symbols above).

## Notes & tips
- If training locally you will need a GPU for reasonable times; otherwise use the provided pretrained artifacts in [wk2_modelling/models](wk2_modelling/models) and [wk2_modelling/histories](wk2_modelling/histories).
- Use the notebooks in order: first run the setup cells at the top of each notebook to ensure paths and imports are correct.
- For reproducing Docker/cloud steps, follow the respective notebook cells exactly — they contain the commands and screenshots.

...existing code...