##Cocktail Data Ingestion

###Overview
Understanding the API:
Started by analyzing the data returned by the API to figure out what’s important and how to organize it in a way that makes sense for easy use.
Deciding on Data Format:
At first, I thought about using a database, like MongoDB, for scalability, flexibility, ease of querying, and great for working with semi-structured data.
But then, I realized the dataset is small- doesn’t change often and might not need the complexity of a database at the moment, so keeping things simple with a JSON file made more sense.
Real-Time vs. Batch Processing:
I considered whether to process the data in real-time (as it’s being fetched) or in batches (all at once after fetching).
Since the API data doesn’t change often and isn’t time-sensitive, real-time processing would be unnecessary and more complex.
The API lets you fetch small, manageable chunks of data (one letter at a time), which works perfectly for batch processing.
Why Batch Processing:
Batch processing is simpler and works well here because:
The data doesn’t need to be processed immediately.
Processing it all together at the end avoids unnecessary effort and makes the workflow smoother.
Writing all the data to a single JSON file in one go is more efficient than constantly opening and closing files.
Final Implementation:
Fetch all the cocktail data from the API (A-Z) at once.
The data is processed and cleaned up in batches, then saved into a single JSON file.
This keeps things straightforward, efficient, and easy to maintain.
