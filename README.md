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
