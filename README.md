# AWS_Sagemaker
# SageMaker XGBoost Model Deployment

## Overview

This repository contains a Jupyter Notebook demonstrating the end-to-end process of training an XGBoost model using the SageMaker built-in algorithm. The model is then deployed as an endpoint for making predictions, and resources are cleaned up after usage.

## Prerequisites

Before running the notebook, ensure you have the following:

- An AWS account with appropriate permissions for SageMaker, S3, and EC2.
- Jupyter Notebook environment with the required libraries installed (`sagemaker`, `boto3`, `pandas`, etc.).

## Steps

### 1. Import Necessary Libraries

- `sagemaker`: for SageMaker functionality
- `boto3`: AWS SDK for Python
- `get_image_uri`: to get the XGBoost container image URI
- `s3_input`, `Session`: for handling S3 inputs and sessions

### 2. Creating S3 Bucket

- Create an S3 bucket for storing training data, test data, and model output.
- Set the output path where the trained model will be saved.

### 3. Downloading the Dataset and Storing in S3

- Use `urllib` to download the dataset.
- Load the dataset into a Pandas DataFrame.
- Split the dataset into training and testing sets.

### 4. Saving Train and Test Data into Buckets

- Save train and test data into S3 buckets.
- Use the `sagemaker.s3_input` class to handle S3 input data.

### 5. Building XGBoost Model with SageMaker

- Use the `get_image_uri` method to get the XGBoost container.
- Set hyperparameters for the XGBoost algorithm.
- Create a SageMaker estimator for training.
- Fit the estimator with the training and validation data.

### 6. Deploy the Machine Learning Model as Endpoints

- Deploy the trained model as an endpoint using the `deploy` method.

### 7. Prediction of the Test Data

- Use the deployed endpoint to make predictions on the test data.

### 8. Deleting the Endpoints and Cleaning Up

- Delete the deployed endpoint and clean up the S3 bucket.

## Usage

Follow the steps outlined in the Jupyter Notebook to train, deploy, and make predictions using the XGBoost model.

## Note

- The code is designed for educational purposes and may need adjustments for specific use cases.
- Update the `bucket_name` variable to a unique name for your S3 bucket.

Feel free to expand on each step with explanations, add troubleshooting tips, and include any additional details that might be helpful for someone following your notebook.

