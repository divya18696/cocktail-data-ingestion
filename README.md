## Cocktail Data Ingestion

### Overview
This program fetches cocktail data from **TheCocktailDB API**, processes it into a standard format, and saves it in a JSON file. It is designed to handle unit conversions, normalize data and log the entire process for debugging.

### Understanding the API
Started by analyzing the data returned by TheCocktailDB API to figure out what’s important and how to organize it in a way that makes sense for ease of use.

### Deciding on Data Format
At first, considered using a database, like MongoDB, for scalability, flexibility, and ease of querying and is also great for working with semi-structured data, but then realized:
- The dataset is relatively small.
- The data doesn’t seem to change often.
- Using a database might introduce unnecessary complexity.
Given these points, decided to keep things simple by storing the data in a **JSON file**.

### Real-Time vs. Batch Processing
Also had to decide whether to process the data in real-time (as it's being fetched) or in batches (all at once after fetching).
- Real-time processing felt unnecessary and more complex because:
    - The data doesn’t change frequently.
    - It’s not time-sensitive.
- The API allows fetching small, manageable chunks of data (one letter at a time), making batch processing a much better option.

### Why Batch Processing
Batch processing was a clear choice due to the following reasons:
- Data doesn’t need to be processed immediately – there’s no need for real-time updates.
- Processing everything at once reduces unnecessary effort and makes the workflow smoother.
- Writing all the data to a single JSON file in one go is more efficient than constantly opening and closing the file.

### Final Implementation
1. Fetch all cocktail data from the API (A-Z).
2. The data is processed and cleaned up in batches.
3. Once the processing is done, it is saved into a single JSON file.
This approach keeps things straightforward, efficient, and easy to maintain, while avoiding unnecessary complexity.

### Conclusion
This project demonstrates a way to ingest, transform, and save the cocktail data for further use.

### How to Run the Code

#### Install Required Libraries
Ensure Python 3.x is installed.

#### Install dependencies
You need to install the required dependencies using **pip**:
```bash
pip install requests
