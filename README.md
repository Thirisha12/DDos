# ⚙ How to Run the Code  

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
- Open net_server.ipynb
- Run the respective method cell to start the federated server
- The server will wait for updates from clients

### *Step 5: Run Clients*
- Open net_flash_C1.ipynb (Client 1) and run all cells
- Open net_flash_C2.ipynb (Client 2) and run all cells
- Both clients will process data using Spearman, MI, and Threshold-Based methods
- Clients will send their updates to the federated server

### *Step 6: Model Aggregation & Retraining*
- Once all client updates are received, the server will aggregate the models
- The server will then retrain using the combined knowledge

### *Step 7: Evaluate Performance*
- The final aggregated model will be evaluated
- Check the performance metrics in the server output logs
- You can also save results in the results/ folder
