---
title: "Cybersecurity Chatbot with Rasa NLU and Large Language Models"
start_date: 2024-08-01
end_date: 2024-08-01
thumbnail: "/assets/images/rasa-small.png"
header:
  image: "/assets/images/rasa.png"
permalink: /projects/cybersecurity-chatbot
tags: [UVU, Artificial Intelligence, Natural Language Processing, Python]
---
## Project Overview
This project aimed to build a user-friendly cybersecurity chatbot that answers queries about security threats and best practices. Leveraging the Rasa framework for natural language understanding (NLU) and dialogue management, I integrated large language models (LLMs) like Cohere to enhance responses.

## Technologies Used
- **Rasa** for NLU and chatbot dialogue flow    
- **Cohere LLM** for contextualized answers    
- **Python** for backend integration and preprocessing    

## Challenges
Initially, integrating LLMs like OpenAI and Google's PaLM API was problematic due to quota limits and paywalls. Hugging Face Transformers was functional but provided unsatisfactory responses. Ultimately, Cohere proved to be the most effective, offering accurate, context-aware responses.

## Screenshots
<img width="855" alt="Screenshot 2024-09-13 at 5 17 15 PM" src="https://github.com/user-attachments/assets/7ee3cf44-6ef5-4799-9b05-716ae028a303">
<img width="1080" alt="Screenshot 2024-09-13 at 5 17 43 PM" src="https://github.com/user-attachments/assets/5a0cb046-336f-4407-9959-d94e9f30310c">

## Results
The chatbot handles user queries on cybersecurity threats like phishing and malware effectively. It successfully provides contextual recommendations while gracefully managing ambiguous queries through fallback mechanisms.

## Future Work
- Expanding the training dataset to cover more specialized cybersecurity topics
- Incorporating more robust fallback handling
- Deploying the chatbot for real-world testing and collecting feedback for further improvement.

## Technical Report
<div style="width: 100%; height: 300px; overflow: hidden;">
  <embed src="/assets/pdf/cybersecurity_chatbot_tech_report.pdf" width="100%" height="100%">
</div>
