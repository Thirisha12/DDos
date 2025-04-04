# 4.a Source for Dataset
### *Flash crowd dataset 1 :* https://github.com/Thirisha12/DDos/blob/main/simulated_dataset_1.csv
### *Flash crowd dataset 2 :* https://github.com/Thirisha12/DDos/blob/main/simulated_dataset_2.csv
### *DDoS dataset 1 :* http://cicresearch.ca/CICDataset/ISCX-Tor-NonTor-2017/Dataset/CSVs/
### *DDoS dataset 2 :* https://www.kaggle.com/datasets/aikenkazin/ddos-sdn-dataset

# 4.b Software and Hardware requirements
Software Specifications
The entire implementation, training, and evaluation of this project are performed
on Google Colab, leveraging its cloud-based environment. Below are the specific
software components and libraries used:
### *1. Platform:* Google Colab
Environment: Linux-based virtual environment (typically running Ubuntu,
although this is abstracted within Colab’s setup).
Python Version: Python 3.10, which is pre-installed in Colab, providing
compatibility with machine learning and data science libraries.

### *2. Libraries Frameworks:*
*Pandas:* Essential for data manipulation and analysis. Used to load, clean, and preprocess data from multiple Nodes, specifically for reading CSV files and structuring data for model input and analysis.
*Scikit-Learn:* Used for machine learning evaluation metrics and model training. Specifically, accuracy score from Scikit-Learn calculates the accuracy of the aggregated model and correlation analysis is applied for potential stacking or additional classification.
*Flask:* A lightweight Python web framework used to build and deploy backend APIs. In this project, it facilitates communication between federated Nodes and the server by exposing RESTful endpoints for model updates, predictions, and aggregations.
*Google Colab Integration Tools:* drive.mount(’/content/drive’): This allows seamless access to Google Drive, where datasets are stored, providing persistent storage across sessions.
*NumPy:* For handling numerical operations and assisting in efficient computation during data transformations.
*Matplotlib Seaborn (optional):* These libraries are available for data visualization, useful for visual analysis of traffic patterns or prediction results.
*3. Environment-Specific Tools:*
Google Colab GPUs/TPUs: The code is compatible with Colab’s hardware accelerators like GPUs or TPUs, which can be activated to speed up computations, particularly for large datasets.

# 4.c How to Run the Code  

### *Step 1: Open the Project in an Editor*  
You can run the code in:  
- *Jupyter Notebook* (Recommended)  
- *Google Colab*  
- *VS Code (With Jupyter Extension)*  

### *Step 2: Get and Upload the Datasets*  
- You need *two datasets* (one for each client).  
- Place them inside the data/ directory for each client.  

For *Jupyter Notebook / Google Colab*, upload manually or run:  
```python
from google.colab import files
uploaded = files.upload()
```
### *Step 3: Install Dependencies*
- Run the following command:
```python
pip install -r requirements.txt
```

### *Step 4: Start the Federated Server*
- Open Server.ipynb
- Run the respective method cell to start the federated server
- The server will wait for updates from clients

### *Step 5: Run Clients*
- Open Client1.ipynb and run all cells
- Open Client2.ipynb and run all cells
- Both clients will process data using Spearman, MI, and Threshold-Based methods
- Clients will send their updates to the federated server

### *Step 6: Model Aggregation & Retraining*
- Once all client updates are received, the server will aggregate the models
- The client will then retrain using the combined knowledge

### *Step 7: Evaluate Performance*
- The final aggregated model will be evaluated
- Check the performance metrics in the server output logs
- You can also save results in the results/ folder
