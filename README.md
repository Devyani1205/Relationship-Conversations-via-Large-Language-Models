
#Overview:-
## This project presents a relationship-oriented chat application powered by Large Language Models (LLMs) and the LangChain framework. The system is designed to offer users intelligent suggestions to improve their sentences and responses based on both current input and historical conversation context.

📌 Key Features Personalized Sentence Suggestions: The system suggests alternative, emotionally intelligent responses to improve sentence clarity, tone, and engagement.

Sentiment Detection: It identifies the emotional tone of each user input and provides contextually relevant suggestions.

Contextual Awareness: Retrieves past conversation context from Pinecone, ensuring each response is grounded in previous interactions.

Integration with Gemini API: Uses Gemini API to generate improved sentence suggestions that account for the emotional dynamics of the conversation.

Conversation Summary Buffer Memory: Stores the conversation history and summarizes it for future use, balancing relevance and conciseness.

Technologies Used Pinecone: A vector database used for efficient context retrieval based on semantic similarity, storing conversation history.

Gemini API: A powerful language model used to generate sentence suggestions based on user inputs.

LangChain Framework: Provides easy-to-use integrations and tools for building conversational AI systems, such as embeddings and memory management.

Sentence Transformers: Used to generate sentence embeddings for semantic similarity matching.

TextBlob: A library for sentiment analysis used to analyze the emotional tone of user inputs.


## **Detailed Workflow Flowchart**

Based on the `conversation-suggestion-rag.ipynb` notebook structure, here's a comprehensive copyable flowchart:

```
┌─────────────────────────────────────────────────────────────────────┐
│                     RELATIONSHIP CONVERSATION RAG SYSTEM              │
└─────────────────────────────────────────────────────────────────────┘

                              ╔════════════════╗
                              │   START SYSTEM  │
                              ╚════════════════╝
                                      │
                                      ▼
                      ┌─────────────────────────────┐
                      │   INITIALIZE RAG PIPELINE    │
                      │ • Load LLM (Google Gemini)   │
                      │ • Setup Vector Store         │
                      │ • Load Embeddings Model      │
                      └─────────────────────────────┘
                                      │
                                      ▼
                      ┌─────────────────────────────┐
                      │  LOAD RELATIONSHIP DATA      │
                      │ • Parse Documents/Prompts    │
                      │ • Generate Embeddings        │
                      │ • Store in Vector DB         │
                      └─────────────────────────────┘
                                      │
                                      ▼
                              ┌───────────────┐
                              │ USER INPUT     │
                              │ INTERACTION    │
                              └───────────────┘
                                      │
                 ┌────────────────────┴────────────────────┐
                 │                                         │
                 ▼                                         ▼
    ┌─────────────────────────┐          ┌─────────────────────────┐
    │  SELECT CONTEXT/TOPIC    │          │ CHOOSE CONVERSATION    │
    │                          │          │ SCENARIO               │
    │ • Relationship Stage     │          │                        │
    │ • Communication Style    │          │ • Conflict Resolution  │
    │ • Emotional State        │          │ • Deep Connection      │
    │ • Specific Challenge     │          │ • Casual Chat          │
    └─────────────────────────┘          │ • Future Planning      │
             │                           └─────────────────────────┘
             │                                     │
             └─────────────────┬───────────────────┘
                               │
                               ▼
                 ┌─────────────────────────────────┐
                 │  RETRIEVE RELEVANT CONTEXT      │
                 │  (Vector Similarity Search)      │
                 │                                 │
                 │ • Query Vector Database         │
                 │ • Find Top-K Similar Contexts   │
                 │ • Rank by Relevance            │
                 └─────────────────────────────────┘
                               │
                               ▼
                 ┌─────────────────────────────────┐
                 │  GENERATE CONVERSATION PROMPT   │
                 │                                 │
                 │ • Build Context Window          │
                 │ • Include Retrieved Examples    │
                 │ • Add User Preferences          │
                 │ • Create System Instructions    │
                 └─────────────────────────────────┘
                               │
                               ▼
                 ┌─────────────────────────────────┐
                 │  LLM PROCESSING                 │
                 │  (Google Gemini)                │
                 │                                 │
                 │ • Analyze Conversation Context  │
                 │ • Generate Suggestions          │
                 │ • Ensure Relationship Health    │
                 │ • Add Emotional Intelligence    │
                 └─────────────────────────────────┘
                               │
                               ▼
                 ┌─────────────────────────────────┐
                 │  POST-PROCESSING & FILTERING    │
                 │                                 │
                 │ • Validate Response Quality     │
                 │ • Check for Sensitivity         │
                 │ • Format Output                 │
                 │ • Add Explanations              │
                 └─────────────────────────────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
                 ▼                           ▼
    ┌──────────────────────┐    ┌──────────────────────────┐
    │  CONVERSATION        │    │  ALTERNATIVES/FOLLOW-UPS │
    │  SUGGESTIONS         │    │                          │
    │                      │    │ • Additional Topics      │
    │ • Opening Lines      │    │ • Alternative Approaches │
    │ • Discussion Points  │    │ • Deeper Questions       │
    │ • Responses Ideas    │    │ • Perspective Shifts     │
    │ • Emotional Cues     │    │ • Resources/Tips         │
    └──────────────────────┘    └──────────────────────────┘
                 │                           │
                 └─────────────┬─────────────┘
                               │
                               ▼
                 ┌─────────────────────────────────┐
                 │  DISPLAY OUTPUT TO USER         │
                 │                                 │
                 │ • Formatted Suggestions         │
                 │ • Confidence Scores             │
                 │ • Additional Context            │
                 │ • User Feedback Option          │
                 └─────────────────────────────────┘
                               │
                 ┌─────────────┴──────────────┐
                 │                            │
                 ▼                            ▼
    ┌──────────────────────┐    ┌──────────────────────┐
    │  SAVE CONVERSATION   │    │  CONTINUE DIALOG     │
    │  HISTORY             │    │  OR NEW QUERY        │
    │                      │    │                      │
    │ • Store User Input   │    │ • Refine Request     │
    │ • Save Response      │    │ • Ask Follow-ups     │
    │ • Track Preferences  │    │ • Explore Related    │
    │ • Learn from Use     │    └──────────────────────┘
    └──────────────────────┘              │
             │                            │
             └────────────────┬───────────┘
                              │
                              ▼
                        ┌──────────────┐
                        │  END SESSION │
                        │   OR LOOP    │
                        └──────────────┘
```

---

## **Detailed Component Descriptions**

### **1. USER INPUT LAYER**
- **Relationship Context**: Current relationship stage, communication patterns
- **Emotional State**: How both parties are feeling
- **Challenge Type**: Specific conflict or topic to address
- **Preferences**: Tone, depth, directness of suggestions

### **2. RETRIEVAL LAYER (RAG)**
- **Vector Embedding**: Converts user input to vector space
- **Similarity Search**: Finds most relevant conversation examples
- **Context Ranking**: Orders by relevance and quality
- **Dynamic Filtering**: Removes irrelevant or harmful suggestions

### **3. PROCESSING LAYER (LLM)**
- **Prompt Engineering**: Structures context for Gemini
- **Temperature Control**: Adjusts creativity vs. consistency
- **Constraint Application**: Ensures healthy relationship guidance
- **Output Validation**: Checks for quality and appropriateness

### **4. OUTPUT LAYER**
```
✓ Conversation Starters
✓ Discussion Topics
✓ Response Suggestions
✓ Emotional Cues to Notice
✓ Follow-up Questions
✓ Alternative Approaches
```

---

## **Copy-Paste Markdown Flowchart (Alternative ASCII Format)**

```
START
  ↓
[INITIALIZE RAG SYSTEM]
  ↓
[LOAD RELATIONSHIP DATA]
  ↓
[USER PROVIDES INPUT]
  ├→ Select Relationship Context
  ├→ Choose Conversation Scenario
  ├→ Specify Emotional State
  └→ Set Preferences
  ↓
[RETRIEVE RELEVANT EXAMPLES FROM VECTOR DB]
  ↓
[BUILD CONTEXT WINDOW]
  ↓
[SEND TO GEMINI LLM]
  ├→ Analyze Context
  ├→ Generate Suggestions
  └→ Apply Relationship Wisdom
  ↓
[POST-PROCESS OUTPUT]
  ├→ Validate Quality
  ├→ Check Sensitivity
  └→ Format Response
  ↓
[DISPLAY SUGGESTIONS TO USER]
  ├→ Conversation Starters
  ├→ Discussion Topics
  ├→ Response Ideas
  └→ Follow-up Options
  ↓
[USER FEEDBACK & ITERATION]
  ├→ Refine Request (LOOP)
  └→ Save & End Session
  ↓
END
```

---

## **Quick Reference: Data Flow**

| Stage | Input | Process | Output |
|-------|-------|---------|--------|
| **Setup** | Configuration | Initialize LLM + Vector DB | Ready System |
| **Input** | User Query | Embed & Validate | Vector Query |
| **Retrieval** | Query Vector | Search Similarity | Top-K Contexts |
| **Processing** | Context + Examples | LLM Generation | Draft Response |
| **Validation** | Draft | Check Quality/Safety | Validated Suggestions |
| **Output** | Suggestions | Format & Present | User-Friendly Response |


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

