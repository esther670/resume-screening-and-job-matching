# resume-screening

## Problem Statement
In today’s competitive job market, recruiters face the critical task of manually screening thousands of resumes for limited job openings. This process is time-consuming, prone to bias, and often fails to identify the most suitable candidates. There is a pressing need for an automated, intelligent system that can accurately and efficiently screen resumes by understanding the contextual meaning of both resumes and job descriptions.

## Project Overview
This project proposes an automated resume screening and job recommendation system that leverages Natural Language Processing (NLP) techniques to automate and enhance the recruitment process. The system aims to not only match resumes with job descriptions for employer use but also actively recommend suitable job opportunities to candidates based on their CVs.
The system would be using deep learning-based language models and efficient similarity search methods to match resumes with job descriptions. This dual-purpose platform will support both employers and job seekers, creating a more dynamic and intelligent recruitment ecosystem.

The objectives of this project include:
- Get to understand the contextual meaning of both resumes and job descriptions using deep NLP models.
- Provide accurate similarity scoring between candidates and job postings for screening and ranking.
- Recommend the most suitable job opportunities to the applicants based on the content of their resume.
- Enable fast and scalable retrieval of relevant resumes and job matches.

## Project Structure/Methodology
### Collect data
- Sourced the resume dataset from Kaggle, resume data https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset and job postings from the Adzuna API
- The resume data comprises of 24 categories of resume holders i.e. HR, designer, IT, teacher, advocate, business-development, healthcare, fitness, agriculture, BPO, Sales, Consultant, Digital media, automobile, chef, finance, apparel, engineering, accountant, construction, public-relations, banking, arts and aviation. The comprehensive details of the resume are within the 'Resume_str' column.
- The job postings comprise of 25 job categories i.e. Accounting & finance,  Admin,  Consultancy,  Creative & Design ,  Customer Service,  domestic help and cleaning ,  Engineering, Graduate, Healthcare & Nursing, Hospitality & Catering, HR & Recruitment, IT, Legal, Logistics & Warehouse, Maintenance, Manufacturing, Part time,  other/general,  PR Advertising &Marketing, Property, retail, Sales,  Social work, Teaching and Trade  & Construction.


### Modelling
- Use of Sentence Bidirectional Encoder Representations from Transformers (S-BERT) as it is good for sentence similarity tasks such as this, since we are comparing the resumes to the job descriptions, provides contextual meaning of the sentences, can handle variability and is computationally efficient compared to BERT.
- Compare the performance of S-BERT against Voyage embeddings which are pre-trained models that produce sentence-level embeddings, just like SBERT.
- Paired the SBERT and Voyage embeddings with FAISS (Facebook AI Similarity Search) which comes in quite handy when performing the similarity search between the two datasets as it enables fast and scalable similarity search across large collections of embeddings. 
- The voyage embeddings appear to be have a higher similarity score compared to SBERT 

### Expected output
A functional system capable of screening and ranking resumes based on a given job description with a ranked list of resumes with similarity scores for each search. 

### Evaluation 
Evaluated the SBERT and Voyage AI embeddings using the silhouette score and specified the metrics on cosine similarity. Despite the scores registered being relatively low, SBERT embeddings seem wto be performing better on the resumes as compared to the VoyageAI which is doing better on the job embeddings as illustrated below:
* Silhouette Scores:
    **SBERT Resumes: 0.1184**
    SBERT Jobs: 0.0898
    VoyageAI Resumes: 0.1070
    **VoyageAI Jobs: 0.1024**
