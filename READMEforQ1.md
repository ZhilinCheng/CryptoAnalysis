For order book data fetching, I use the Deribit API and employ async to speed up the process.
The reason for setting a batch size is to avoid issues such as rejection from Deribit due to sending too many requests at once. 
By introducing batching, I slow down the program to ensure it stays within the API's rate limits and avoids being blocked.
