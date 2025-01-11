# NBA_data_lake
# 🏀 NBA Sports Analytics Data Lake  

## 📖 Project Overview  
This project demonstrates how to build a **cloud-native data lake** for analyzing NBA player data. It leverages **AWS services** like S3, Glue, and Athena to fetch, store, organize, and query player statistics in real time.  

## 🚀 Features  
- Fetch real-time NBA player data from [Sportsdata.io](https://sportsdata.io).  
- Store raw data in **Amazon S3** as line-delimited JSON files.  
- Organize data using **AWS Glue** for structured queries.  
- Enable SQL-based analytics using **Amazon Athena**.  

---

## 🛠️ Technologies Used  
- **Programming Language:** Python  
- **Cloud Services:**  
  - Amazon S3  
  - AWS Glue  
  - Amazon Athena  
- **API:** Sportsdata.io  
- **Environment Management:** Python `dotenv` library for secure API key management  

---

## 📋 Project Setup  

### 1. Prerequisites  
- AWS account with permissions for S3, Glue, and Athena.  
- API key from [Sportsdata.io](https://sportsdata.io).  
- Python 3.x installed.  
- Required Python libraries:  
  ```bash
  pip install boto3 python-dotenv requests

2. Environment Configuration

Create a .env file in the project directory and add the following:

SPORTS_DATA_API_KEY=<Your-Sportsdata-API-Key>
NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players

3. AWS Configuration

Set up your AWS CLI credentials:

aws configure

🏗️ How It Works
1. Create an S3 Bucket

The script initializes an S3 bucket to store raw NBA player data.
2. Fetch Data from Sportsdata.io

Data is fetched via the NBA endpoint using a secure API key.
3. Store Data in S3

The fetched data is transformed into line-delimited JSON format and uploaded to the S3 bucket.
4. Organize Data with Glue

A Glue database and table are created to catalog the data for querying.
5. Query Data with Athena

Athena is configured to analyze the data using SQL queries, with query results stored in a dedicated S3 folder.
📂 Project Structure

├── main.py                # Main script for data lake setup  
├── .env                   # Environment variables (not included in the repo)  
├── README.md              # Project documentation  
├── requirements.txt       # Python dependencies  

🚀 Running the Project

    Clone the repository:

git clone <repository-url>
cd <repository-folder>

Install dependencies:

pip install -r requirements.txt

Run the script:

    python main.py

📊 Example SQL Query with Athena

SELECT FirstName, LastName, Team, Points  
FROM nba_players  
WHERE Points > 20  
ORDER BY Points DESC;  

📈 Future Improvements

    Integrate player performance analytics dashboards.
    Add automated data ingestion with AWS Lambda.
    Support additional sports leagues and data sources.

🤝 Contributing

Contributions are welcome! Please feel free to open issues or submit pull requests.
📄 License

This project is licensed under the MIT License. See the LICENSE file for details.
