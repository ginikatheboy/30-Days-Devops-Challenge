<<<<<<< HEAD
# NBADataLake
This repository contains the setup_nba_data_lake.py script, which automates the creation of a data lake for NBA analytics using AWS services. The script integrates Amazon S3, AWS Glue, and Amazon Athena, and sets up the infrastructure needed to store and query NBA-related data.

# Overview
The setup_nba_data_lake.py script performs the following actions:

Creates an Amazon S3 bucket to store raw and processed data.
Uploads sample NBA data (JSON format) to the S3 bucket.
Creates an AWS Glue database and an external table for querying the data.
Configures Amazon Athena for querying data stored in the S3 bucket.

# Prerequisites
Before running the script, ensure you have the following:

Go to Sportsdata.io and create a free account
At the top left, you should see "Developers", if you hover over it you should see "API Resources"
Click on "Introduction & Testing"

Click on "SportsDataIO API Free Trial" and fill out the information & be sure to select NBA for this tutorial

You will get an email and at the bottom it says "Launch Developer Portal"

By default it takes you to the NFL, on the left click on NBA

Scroll down until you see "Standings"

You'll "Query String Parameters", the value in the drop down box is your API key. 

Copy this string because you will need to paste it later in the script

IAM Role/Permissions: Ensure the user or role running the script has the following permissions:

S3: s3:CreateBucket, s3:PutObject, s3:DeleteBucket, s3:ListBucket
Glue: glue:CreateDatabase, glue:CreateTable, glue:DeleteDatabase, glue:DeleteTable
Athena: athena:StartQueryExecution, athena:GetQueryResults

# START HERE 
# Step 1: Open CloudShell Console

1. Go to aws.amazon.com & sign into your account

2. In the top, next to the search bar you will see a square with a >_ inside, click this to open the CloudShell

# Step 2: Create the setup_nba_data_lake.py file
1. In the CLI (Command Line Interface), type
```bash
nano setup_nba_data_lake.py
```


2. In another window, go to [GitHub](https://github.com/alahl1/NBADataLake)

-Copy the contents inside the setup_nba_data_lake.py file

-Go back to the Cloudshell window and paste the contents inside the file.

3. Find the line of code under #Sportsdata.io configurations that says "api_key" 
paste your api key inside the quotations

4. Press ^X to exit, press Y to save the file, press enter to confirm the file name 


# Step 3: Create .env file
1. In the CLI (Command Line Interface), type
```bash
nano .env
```
2. paste the following line of code into your file, ensure you swap out with your API key
```bash
SPORTS_DATA_API_KEY=your_sportsdata_api_key
NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players
```

3. Press ^X to exit, press Y to save the file, press enter to confirm the file name 


# Step 4: Run the script
1. In the CLI type
```bash
python3 setup_nba_data_lake.py
```
-You should see the resources were successfully created, the sample data was uploaded successfully and the Data Lake Setup Completed

# Step 5: Manually Check For The Resources
1. In the Search Bar, type S3 and click blue hyper link name

-You should see 2 General purpose bucket named "Sports-analytics-data-lake"

-When you click the bucket name you will see 3 objects are in the bucket

2. Click on raw-data and you will see it contains "nba player data.json"

3. Click the file name and at the top you will see the option to Open the file

-You'll see a long string of various NBA data

4. Head over to Amazon Athena and you could paste the following sample query:
```bash
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
```

-Click Run
-You should see an output if you scroll down under "Query Results"

### **What We Learned**
1. Securing AWS services with least privilege IAM policies.
2. Automating the creation of services with a script.
3. Integrating external APIs into cloud-based workflows.


### **Future Enhancements**
1. Automate data ingestion with AWS Lambda
2. Implement a data transformation layer with AWS Glue ETL
3. Add advanced analytics and visualizations (AWS QuickSight)

=======
# Weather Dashboard & AWS Infrastructure Project

## Overview
A Python-based weather dashboard application that integrates with OpenWeather API and AWS S3 to fetch and store real-time weather data for cities. The project demonstrates cloud infrastructure management and automation using AWS CLI.

## Features
- Real-time weather data fetching using OpenWeather API
- Automated AWS S3 bucket management
- Secure cloud storage implementation
- Region-specific AWS configurations
- Environment variable management for secure credential handling

## Technologies Used
- Python
- AWS S3
- AWS CLI
- boto3 (AWS SDK for Python)
- OpenWeather API
- python-dotenv

## Prerequisites
- Python 3.x
- AWS Account
- AWS CLI configured with appropriate permissions
- OpenWeather API key

## Setup Instructions
1. Clone the repository
```bash
git clone [repository-url]
cd [repository-name]
```

2. Install required dependencies
```bash
pip install -r requirements.txt
```

3. Configure environment variables
Create a `.env` file in the project root with:
```env
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
AWS_REGION=your_preferred_region
OPENWEATHER_API_KEY=your_api_key
```

4. Configure AWS CLI
```bash
aws configure
```

## Usage
1. Run the weather dashboard application:
```bash
python weather_dashboard.py
```

2. For S3 bucket management:
```bash
python s3_manager.py
```

## Project Structure
```
├── weather_dashboard.py
├── s3_manager.py
├── requirements.txt
├── .env
└── README.md
```

## Common Issues and Solutions
1. **IllegalLocationConstraintException**
   - Ensure the correct region is specified in AWS configuration
   - Verify bucket name availability in the chosen region

2. **AccessDenied Issues**
   - Check IAM permissions for your AWS user
   - Verify AWS credentials in environment variables
   - Ensure bucket policies are correctly configured

## Best Practices Implemented
- Secure credential management using environment variables
- Error handling for API requests and S3 operations
- Region-specific configurations for optimal performance
- Proper logging and debugging mechanisms

## Future Improvements
- [ ] Add support for multiple cities monitoring
- [ ] Implement data visualization features
- [ ] Add automated testing
- [ ] Create CI/CD pipeline
- [ ] Add monitoring and alerting capabilities

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details

## Acknowledgments
- OpenWeather API for weather data
- AWS Documentation
- Python boto3 community

## Connect
Feel free to connect with me on [LinkedIn](www.linkedin.com/in/okeke-jehohanan-a46365120) for more DevOps and cloud computing discussions!
>>>>>>> 24b949966c54dde2915c821905be863b3520024f
