import json
import os
import boto3
import urllib3
from datetime import datetime

# Initialize S3 and HTTP client outside handler for connection reuse
s3 = boto3.client('s3')
http = urllib3.PoolManager()

def lambda_handler(event, context):
    # 1. Configuration
    api_key = #os.environ.get('FMP_API_KEY') #'8a3RRtooAiZzAdP5QSaBEPs8PB87rjqD' 
    bucket_name = os.environ.get('S3_BUCKET_NAME') #'raw-us-east-1-jngai-dev'
    
    if not api_key or not bucket_name:
        return {
            'statusCode': 500,
            'body': json.dumps('Error: Missing FMP_API_KEY or S3_BUCKET_NAME.')
        }
#
    # 2. Fetch Data (Stable Endpoint, Limit 3)
    url = f"https://financialmodelingprep.com/stable/fmp-articles?page=0&limit=3&apikey={api_key}"
    print(f"Fetching from: {url.replace(api_key, 'HIDDEN')}")

    try:
        response = http.request('GET', url)
        
        if response.status != 200:
            print(f"API Error: {response.status} - {response.data.decode('utf-8')}")
            return {'statusCode': response.status, 'body': "Failed to fetch data."}
            
        # Parse data to ensure it is valid JSON before saving
        data = json.loads(response.data.decode('utf-8'))
        
    except Exception as e:
        print(f"Fetch Exception: {str(e)}")
        return {'statusCode': 500, 'body': f"Error fetching data: {str(e)}"}

    # 3. Save to S3
    timestamp = datetime.now().strftime("%Y-%m-%d_%H-%M-%S")
    file_name = f"fmp_articles_{timestamp}.json"
    
    try:
        s3.put_object(
            Bucket=bucket_name,
            Key=file_name,
            Body=json.dumps(data),
            ContentType='application/json'
        )
        print(f"Success: Saved to s3://{bucket_name}/{file_name}")
        
    except Exception as e:
        print(f"S3 Upload Exception: {str(e)}")
        return {'statusCode': 500, 'body': f"Error uploading to S3: {str(e)}"}

    return {
        'statusCode': 200,
        'body': json.dumps(f"Saved {len(data)} articles to {file_name}")
    }
