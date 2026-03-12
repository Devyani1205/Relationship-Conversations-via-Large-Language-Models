🗣️ #Effective Conversations via Large Language Models

This project presents a relationship-oriented chat application powered by Large Language Models (LLMs) and the LangChain framework. The system is designed to offer users intelligent suggestions to improve their sentences and responses based on both current input and historical conversation context.

📌 Key Features
Personalized Sentence Suggestions: The system suggests alternative, emotionally intelligent responses to improve sentence clarity, tone, and engagement.

Sentiment Detection: It identifies the emotional tone of each user input and provides contextually relevant suggestions.

Contextual Awareness: Retrieves past conversation context from Pinecone, ensuring each response is grounded in previous interactions.

Integration with Gemini API: Uses Gemini API to generate improved sentence suggestions that account for the emotional dynamics of the conversation.

Conversation Summary Buffer Memory: Stores the conversation history and summarizes it for future use, balancing relevance and conciseness.

Technologies Used
Pinecone: A vector database used for efficient context retrieval based on semantic similarity, storing conversation history.

Gemini API: A powerful language model used to generate sentence suggestions based on user inputs.

LangChain Framework: Provides easy-to-use integrations and tools for building conversational AI systems, such as embeddings and memory management.

Sentence Transformers: Used to generate sentence embeddings for semantic similarity matching.

TextBlob: A library for sentiment analysis used to analyze the emotional tone of user inputs.


References:- 

https://medium.com/@michael.j.hamilton/conversational-memory-with-langchain-82c25e23ec60
https://github.com/GoogleCloudPlatform/generative-ai/blob/main/gemini/orchestration/intro_langchain_gemini.ipynb
https://youtu.be/BlAqIS1fEBU?si=x29hoMb-HyCl6ZMd
https://youtu.be/BlAqIS1fEBU?si=N-I8Tmn0BTGeZgG6
https://youtu.be/fizZ9mqY1Fs?si=csv2ZoCR5NALockR
https://youtu.be/s5MMPp_WQok?si=5iQc6cJf3Uc-8P5h
https://youtu.be/A3WKdt_MNZQ?si=HMETw0gRksqvD5-S
https://youtu.be/GgeoyzWBrSI?si=vD4pDQdlbiloQMfT
https://youtu.be/nAKhxQ3hcMA?si=XY8rNQS5hICV4XvM
https://youtu.be/nAKhxQ3hcMA?si=TQDOECMoqgJCEIlJ
https://github.com/pinecone-io/examples/blob/master/docs/pinecone-reranker.ipynb

