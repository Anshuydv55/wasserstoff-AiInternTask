# Domain-Specific PDF Summarization & Keyword Extraction Pipeline 

# Project Summary
The purpose of this project is to automate the process of downloading, extracting, summarizing, and indexing content from PDF files using a specified dataset of URLs. The outcome is a streamlined system that efficiently stores metadata, summaries, and keywords into a MongoDB database, making it easier to access and analyze large amounts of PDF data.

# Problem Statement
Design and implement a dynamic pipeline that processes multiple PDF documents from a desktop folder, generates domain-specific summaries and keywords, and stores them in a MongoDB database. The system must efficiently handle documents of varying lengths, from short to long, and update the database with summary and keyword data after each document is processed.

# Approach Breakdown

I start with downloading necessary librarires such as  pymongo for MongoDB interactions, pdfplumber for PDF text extraction, and requests for downloading files.

Loaded a JSON dataset containing URLs of the PDFs to be processed and established a connection to a local MongoDB database named pdf_summarization.

Implemented a function to download each PDF from the provided URLs, saving them locally with unique filenames.

reated a function to extract text from each PDF using pdfplumber, gathering metadata such as file name, path, size, and number of pages, and stored this data in MongoDB.

Developed a text summarization function that identifies the top five sentences based on word frequency, generating concise summaries of the extracted text.

Implemented a keyword extraction function that filters out common stop words, identifying the top ten most common keywords from the text.

Built a processing pipeline to handle multiple PDFs concurrently using ThreadPoolExecutor, significantly improving the speed of downloading and processing.

Updated MongoDB entries with the generated summaries and keywords for efficient data retrieval.

Calculated the total processing time for the operation to evaluate and enhance efficiency.

# Results:
# > Efficiency: The use of threading allowed the project to handle multiple PDFs simultaneously, greatly reducing processing time.
# > Data Structure: Each PDF's metadata, along with its extracted text, summary, and keywords, is stored in a structured manner in MongoDB.
# > Outcome: Successfully processed all PDFs in the dataset, with results stored and easily accessible for future analysis.
