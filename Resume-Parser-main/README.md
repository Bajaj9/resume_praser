# Resume-Parser
- This was a group project built in a team of 5 people for the course IC-272 Data Science III.  
- It is an ML model which takes resume as an input, infer details from it and then predict whether the resume is capable of being selected for a certain job position.  
- All the necessary code is present within the ResumeParser.ipynb file.
- The output and working of the project can be understood using the link given below.  
Project video: [YouTube link](https://www.youtube.com/watch?v=lIcSQqbD5C4)
### Project Overview:

1. Preparing the training data to make it compatible with SpaCy and then utilizing a Docbin object to store data in a .spacy file format.
2. Developing a .config file and training a customized Named Entity Recognition (NER) model using SpaCy.
3. Accepting input in the form of resumes and job profiles, which can be in PDF or Doc format, and converting them into text.
4. Analyzing the resume content and comparing it with the job profile using Cosine Similarity.
