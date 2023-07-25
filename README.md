# NLP Abstractive Text Summarizer
# (An End-To-End ML Project using Pytorch)

#### Important Notes: 
If Cloning this project, it is importent is note that in ```src/textSummarizer/components/model_trainer.py```, the trainset is set to testset for the sake of a shorter training time due to limited hardware resources. You can control output length and model penalties in ```src/textSummarizer/pipeline/predict```. Training in reasonable time depends on your hardware.

If you just want to run pipeline and not the app run ```python3 main.py```

## Motivation

This project was inspired by an interest of the rise in popularity of NLP due to ChatGPT. Before looking into text generation, I was looking into text summarization and came across a paper about Abstractive Summarization using an architecture called PEGASUS. 

Paper: https://arxiv.org/pdf/1912.08777.pdf   
Model: https://huggingface.co/google/pegasus-cnn_dailymail

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2F149695847.v2.pressablecdn.com%2Fwp-content%2Fuploads%2F2020%2F03%2Fseq2seq-text-summarization.png&f=1&nofb=1&ipt=0f05b7ce29ad249144b7d0c1d2cea4cb5002e4062c93b829c2fcc1a1591e332e&ipo=images" 
    alt="Our logo">
</img>

## Simple Text Summarization Application using FastAPI

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="demo.gif" 
    alt="Our logo">
</img>

## Model Architecture: Pegasus

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmiro.medium.com%2Fmax%2F1280%2F1*3fBR6jQeqlVlb2Ccrx9Bgg.png&f=1&nofb=1&ipt=65528de46ea62bc759d3e172f5b2906f1e22a33fcad7498842e58490798ac234&ipo=images" 
    alt="Our logo">
</img>

## Project / Pipeline Structure

#### For every "stage" added to the pipeline I added to the following in this order

1. Update config.yaml
2. Update params.yaml
3. Update the entity
4. Update the configuration manager in src config
5. Update the components
6. Update the pipeline 
7. Update the main.py




# How do I run this project locally?

### Steps:

#### 1. Clone the repository

```bash
git clone https://github.com/Anish-Mitagar/nlp-text-summarization-project.git
```
#### 2. Create a conda environment after opening the repository

```bash
conda create -n textsum python=3.9 -y
conda activate textsum
```

#### 3. Install the requirements

```bash
pip3 install -r requirements.txt
```

#### 4. Run the app

```bash
python3 app.py
```



# How to do a AWS-CICD Deployment using Github Actions?

### 1. Login to AWS console.

### 2. Create IAM user for deployment

    Add the following policies:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

    Save they access key and secret (download the .csv file when shown)

	
### 3. Create ECR repo to store/save docker image
    - Save the URI for later
    - Example URI:  5283647589263.dkr.ecr.us-east-1.amazonaws.com/{$repo_name}

	
### 4. Create EC2 machine (Ubuntu) 

### 5. Connect to EC2 Machine and install Docker :
	
```bash
sudo apt-get update -y

sudo apt-get upgrade

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

	
### 6. Configure EC2 as self-hosted runner:
    setting => actions => runner => new self hosted runner => choose os => then run command one by one

    (On the EC2 Machine name the runner "self-hosted")


### 7. Setup github secrets:

    AWS_ACCESS_KEY_ID =

    AWS_SECRET_ACCESS_KEY =

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = 

    ECR_REPOSITORY_NAME = 



