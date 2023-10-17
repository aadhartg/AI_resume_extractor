# Description of the Project
This Project provides a tool for extracting information from CVs/Resumes (only in PDF format) using the OpenAI Chat API and storing the results in a MongoDB collection.

## Dependencies
1. openai: OpenAI Python library for API interactions
2. fitz: PyMuPDF library for working with PDF files
3. os: Operating system library for file operations
4. re: Regular expressions library for text preprocessing
5. json: JSON library for handling JSON data
6. db_connection: Custom module for MongoDB connection (provide your own module)

## Requirements
1. Ensure that you have the required dependencies installed (openai, fitz, re, json, etc.).
2. Add a Directory of CVs/Resumes in PDF format in the Folder Directory.
3. Update the db_connection module with your MongoDB connection details (MongoDB URL, yourDatabase, yourCollection).
4. Generate and Add the OpenAI API Key.
5. Customize the code based on your specific requirements and use cases.

## Functioning
After fullfilling all the requirements, you just need to run the main.py file and the code will directly extract the text from the PDF and send it to the ChatGPT also, it will provide the following details :
+ candidate_personal_info,
+ candidate_past_experience,
+ candidate_education_info,
+ candidate_skills,
+ candidate_soft_skills,
+ candidate_achievements

in JSON format and all the data will be stored in the MongoDB.

## For Example :
Following is a sample CV/Resume PDF file

[Download PDF File](https://github.com/aadhartg/AI_resume_extractor/blob/master/ResumeDocs/sample_resume1.pdf)

And this is the data extracted from the pdf file all the information described as above :

```json
{
    "candidate_personal_info": {
        "name": "James Bond",
        "email": "james.bond@mi6.gov",
        "phone": "44 207 123 4567",
        "address": "MI6 Headquarters, London, United Kingdom",
        "website": "www.mi6.gov.uk"
    },
    "candidate_past_experience": [
        {
            "title": "Secret Agent",
            "employer": "MI6 Intelligence Agency",
            "location": "London",
            "start_date": "1962",
            "end_date": "Present",
            "responsibilities": [
                "Covert intelligence operations for national security",
                "Infiltration from high-risk environments",
                "Utilization of advanced espionage techniques and gadgets",
                "Surveillance analysis and threat prevention"
            ]
        }
    ],
    "candidate_education_info": [
        {
            "degree": "Intelligence Academy",
            "university": "MI6 Training Facility",
            "location": "London",
            "start_date": "1962",
            "end_date": "1958",
            "achievements": [
                "Mastered advanced techniques for discreetly gathering intelligence and conducting covert operations",
                "Trained extensively in planning and executing covert operations and infiltrating high-security areas",
                "Received rigorous combat training in martial arts, firearms handling, and tactical skills",
                "Proficient in surveillance methods, countersurveillance techniques, and analyzing gathered intelligence"
            ]
        }
    ],
    "candidate_skills": [
        "Espionage techniques",
        "Surveillance",
        "Combat training",
        "Infiltration",
        "Problem solving",
        "Effective communication",
        "Adaptability",
        "Teamwork"
    ],
    "candidate_soft_skills": [],
    "candidate_achievements": [
        "Uncovered a North Korean general's plan to use a satellite weapon to create a war between North and South Korea",
        "Protected an oil heiress from a terrorist plotting to exploit her family's resources and trigger a global meltdown",
        "Investigated a media mogul's plot to provoke a war between the UK and China for increased ratings and power",
        "Prevented the use of the Goldeneye satellite weapon system by a rogue agent to cause global financial chaos"
    ]
}
```

