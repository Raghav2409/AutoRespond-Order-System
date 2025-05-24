# Fashion Store Email Processing System - Auto Respond & Order Processing

## Overview
This project implements an intelligent email processing system for a fashion store that automatically handles customer inquiries and order requests. The system uses advanced AI techniques to classify emails, process orders, and generate appropriate responses.

## Features

### 1. Email Classification
- Automatically categorizes incoming emails as either "product inquiry" or "order request"
- Uses GPT-4 for accurate intent classification
- Handles various email formats and writing styles

### 2. Order Processing
- Extracts product IDs and quantities from order requests
- Verifies product availability in stock
- Updates inventory levels automatically
- Generates professional order confirmation emails
- Suggests alternatives for out-of-stock items

### 3. Product Inquiry Handling
- Uses TF-IDF and cosine similarity for product matching
- Provides detailed product information
- Generates personalized responses with relevant recommendations
- Handles complex queries about product features and availability

## Technical Implementation

### Dependencies
```python
pandas
numpy
openai
langchain
faiss-cpu
tqdm
gspread
google-auth
gspread-dataframe
regex
rapidfuzz
```

### Key Components

1. **EmailProcessor Class**
   - Unified class handling all email processing tasks
   - Implements vector-based product search
   - Manages Google Sheets integration

2. **Product Matching**
   - Uses FAISS for efficient vector similarity search
   - Implements fuzzy matching for product names
   - Handles partial matches and similar products

3. **Response Generation**
   - Context-aware response generation using GPT-4
   - Professional tone adaptation
   - Includes product details, pricing, and availability

## Setup Instructions

1. Install required packages:
```bash
pip install pandas numpy openai langchain faiss-cpu tqdm gspread google-auth gspread-dataframe regex rapidfuzz
```

2. Configure API Keys:
   - Set up OpenAI API key
   - Configure Google Sheets credentials

3. Run the notebook:
   - Open `Solve_Business_Problems_with_AI_.ipynb` in Jupyter
   - Execute cells in sequence
   - Results will be saved to Google Sheets

## Output Format

The system generates four main outputs:

1. **Email Classification**
   - email_id
   - category (product inquiry/order request)

2. **Order Status**
   - email_id
   - product_id
   - quantity
   - status (created/out of stock)

3. **Order Responses**
   - email_id
   - response (confirmation/out of stock notification)

4. **Inquiry Responses**
   - email_id
   - response (product information/recommendations)

## Best Practices

1. **Error Handling**
   - Robust error handling for API calls
   - Fallback mechanisms for product matching
   - Graceful degradation when services are unavailable

2. **Performance Optimization**
   - Efficient vector search using FAISS
   - Batch processing for multiple emails
   - Caching of product vectors

3. **Security**
   - Secure API key management
   - Data validation and sanitization
   - Access control for Google Sheets

## Limitations

1. API rate limits for OpenAI
2. Token limits for GPT-4 responses
3. Google Sheets API quotas
4. Processing time for large datasets

## Future Improvements

1. Implement caching for frequently accessed products
2. Add support for multiple languages
3. Enhance product matching algorithms
4. Implement real-time stock updates
5. Add support for image-based product queries

## Contributing

Feel free to submit issues and enhancement requests!
