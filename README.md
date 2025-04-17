# resume-screening

## Problem Statement
In today’s competitive job market, recruiters face the critical task of manually screening thousands of resumes for limited job openings. This process is time-consuming, prone to bias, and often fails to identify the most suitable candidates. There is a pressing need for an automated, intelligent system that can accurately and efficiently screen resumes by understanding the contextual meaning of both resumes and job descriptions.

## Project Overview
This project proposes an automated resume screening system that leverages Natural Language Processing (NLP) techniques to automate the recruitment process. The system would be using deep learning-based language models and efficient similarity search methods to match resumes with job descriptions and rank them accordingly.

The objectives of this project include:
- Get to understand the contextual meaning of both resumes and job descriptions.
- Provide accurate similarity scoring between candidates and job postings.
- Enable fast retrieval of relevant resumes.

## Project Structure/Methodology
### Collect data
Sourced the datasets from Kaggle, resume data https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset and job posting https://www.kaggle.com/datasets/akshatkjain/job-postings?resource=download

### Modelling
- Use of Sentence Bidirectional Encoder Representations from Transformers (S-BERT) as it is good for sentence similarity tasks such as this, since we are comparing the resumes to the job descriptions, provides contextual meaning of the sentences, can handle variability and is computationally efficient compared to BERT.
- FAISS (Facebook AI Similarity Search) would come in handy when performing a similarity search between the two datasets. Moreover, it works well with SBERT to enable fast and scalable similarity search across large collections of resume embeddings. 

### Expected output
A functional system capable of screening and ranking resumes based on a given job description with a ranked list of resumes with similarity scores for each search. 
