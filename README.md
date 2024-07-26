# Aurora PostgreSQL Vector Store Sample 

This sample demonstrates how to set up an [Aurora PostgreSQL](https://aws.amazon.com/rds/aurora/) as a vector store for text embeddings generated using models from [Amazon Bedrock](https://aws.amazon.com/bedrock/) and perform similarity searches on the stored vectors. 

Embeddings are dense vector representations of data, such as text, images, or audio, that capture semantic or contextual information. These embeddings are typically learned by machine learning models during the training process, mapping the input data to a lower-dimensional vector space where similar data points are represented by similar vectors.

Vectors, on the other hand, are numerical representations of data points in a multi-dimensional space. They are ordered lists of numbers, where each number represents a value along a specific dimension or feature.

In this sample, we will use a pre-trained model, `amazon.titan-embed-g1-text-02`, available through [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/titan-embedding-models.html), to generate text embeddings. These embeddings will be stored as vectors in an Aurora PostgreSQL database using the vector data type.

## Repository Contents

This repository includes the following:

1. An Amazon CloudFormation template (aurora_sagemaker.yaml) to deploy an Aurora PostgreSQL database cluster and a SageMaker notebook instance.
2. Python notebook (aurora-postgresql-vector.ipynb) 

## Workflow
The workflow for this sample will involve the following steps:

1. Deploy a CloudFormation stack to create an Aurora PostgreSQL database cluster and a SageMaker notebook instance.
2. Generate text embeddings using the pre-trained model from Amazon Bedrock.
3. Store and index the embeddings as vectors in the Aurora PostgreSQL database using pgvector extension.
4. Execute sample text queries and analyze the results to demonstrate the utility of the setup in retrieving textually similar items.

## Getting Started

1. Go to the [AWS CloudFormation console](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1), and click Create Stack.
2. Provide a stack name.
3. Select "Upload a template file" and upload the aurora_sagemaker.yaml file from this repository.
4. On the Options page, click Next.
5. On the Review page, review the details and select the checkbox acknowledging that your template has capabilities to create AWS IAM resources. When finished, click Create. It may take several minutes for the stack to finish creating resources.


## Using the Notebook

1. From the Outputs tab in your CloudFormation console, click the **NotebookInstanceURL**.
2. Click on Open **JupyterLab** under **Actions** and clone this repository.
3. Open aurora-postgresql-vector.ipynb notebook with default kernel and follow the steps in it. 

By following this workflow, you will learn how to use Aurora PostgreSQL as a vector store for text embeddings and perform similarity searches on the stored vectors.
