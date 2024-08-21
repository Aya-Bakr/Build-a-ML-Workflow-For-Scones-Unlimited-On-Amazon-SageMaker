## Build a ML Workflow for Scones Unlimited on Amazon SageMaker

**Description**: This project was built as part of Udacity's AWS ML Fundamentals Program.

**Objective**:  
To develop a scalable and reliable image classification model for Scones Unlimited using Amazon SageMaker.

### Amazon Web Services used:
- **Amazon SageMaker**: A cloud-based machine-learning platform that enables developers to create, train, and deploy machine-learning models.
- **AWS Lambda**: A serverless compute service for running code without managing servers.
- **Amazon Simple Storage Service (S3)**: Cloud object storage for storing and retrieving data.
- **Amazon Step Functions**: A visual serverless orchestration service for creating and managing workflows.
- **AWS Identity and Access Management (IAM)**: A service to securely manage identities and access to AWS services and resources.

### Key Files

1. **`starter.ipynb`**: A Jupyter notebook containing the complete script. It demonstrates the entire machine learning workflow for Image Classification, including:
   - Data Staging
   - Data Preprocessing
   - Data Loading into S3 Bucket
   - Model Training
   - Model Deployment
   - Testing and Evaluation
   - Data Visualization

2. **`lambda.py`**: A Python script containing all the Lambda functions used in the ML Workflow. The Lambda functions are:
   - `serializeImages.py`: Takes input from the S3 bucket, base64 encodes the object data, and returns the serialized data as 'Image data' to the Step Function.
   - `classifyImages.py`: Performs image classification by taking the output of `serializeImages.py` as input and returning inferences to the Step Function.
   - `filterInferences.py`: Filters the inferences based on a low-confidence score, using the output of `classifyImages.py`.

3. **`stepfunction.json`**: An exported JSON file that contains the state machine (Step Function). It uses Amazon States Language, a JSON-based structured language, to define the state machine.

4. **`stepfunctions_graph.png` & `Screenshot Step Function Execution.png`**: Images showcasing the successful implementation of the Step Function and the overall ML workflow.

### Setup Instructions

To replicate this project, follow these steps:

1. **Clone the repository**:  
   ```
   git clone <repository_url>
   ```
   
2. **Install dependencies**:  
   Ensure you have Python and the required packages installed. Use the following command to install dependencies:
   ```
   pip install -r requirements.txt
   ```

3. **Configure AWS Credentials**:  
   Make sure your AWS CLI is configured with appropriate credentials and permissions to access SageMaker, S3, and Lambda.

4. **Run the Jupyter Notebook**:  
   Open `starter.ipynb` in Jupyter and follow the steps to execute the ML workflow.

5. **Deploy Lambda Functions**:  
   Deploy the Lambda functions from `lambda.py` to your AWS environment.

6. **Run Step Functions**:  
   Import `stepfunction.json` into AWS Step Functions and execute the workflow.

### Results

The final results of the project can be visualized through the images provided in the repository. These show the successful execution of the machine learning workflow.
