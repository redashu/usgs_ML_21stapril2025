# Natural Language Processing (NLP)

## Definition
NLP is a subfield of Artificial Intelligence (AI) that focuses on the interaction between computers and human language. It enables machines to read, understand, and derive meaning from text or speech.

## Key Components of NLP

| Component               | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| **Tokenization**        | Splitting text into words, sentences, or symbols.                          |
| **Stemming/Lemmatization** | Reducing words to their root form (e.g., "running" → "run").              |
| **Part-of-Speech (POS) Tagging** | Labeling words as nouns, verbs, adjectives, etc.                     |
| **Named Entity Recognition (NER)** | Identifying names (people, places, organizations).                |
| **Syntax & Parsing**    | Analyzing sentence structure (subject, object, etc.).                      |
| **Semantic Analysis**   | Understanding meaning (e.g., "bank" as a riverbank or financial bank).     |
| **Sentiment Analysis**  | Detecting emotions (positive, negative, neutral).                          |

## Applications of NLP
- **Search Engines** (Google, Bing)
- **Spam Detection** (Gmail)
- **Machine Translation** (Google Translate)
- **Chatbots & Virtual Assistants** (Siri, Alexa)
- **Text Summarization** (News articles)
- **Speech Recognition** (Apple Dictation)

---

# Natural Language Understanding (NLU)

## Definition
NLU is a subset of NLP that focuses on machine comprehension of human language. It goes beyond syntax to extract context, intent, and meaning.

## Key Challenges in NLU
- **Ambiguity Resolution**  
    Example: "He saw the man with glasses."  
    (Who has glasses? The observer or the man?)
- **Sarcasm & Irony Detection**  
    Example: "Great, another meeting!" (Could be sarcastic.)
- **Contextual Understanding**  
    Example: "Apple" (fruit vs. company).

## NLU Techniques

| Technique               | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| **Intent Recognition**  | Detecting user goals (e.g., "Book a flight" → travel intent).               |
| **Entity Extraction**   | Identifying key info (e.g., dates, locations).                             |
| **Coreference Resolution** | Linking pronouns to nouns (e.g., "John said he is happy").               |
| **Semantic Role Labeling** | Identifying "who did what to whom."                                      |

## Applications of NLU
- **Voice Assistants** (Alexa understanding "Play my workout playlist.")
- **Customer Support Bots** (Resolving "My order hasn’t arrived!")
- **Sentiment Analysis for Brands** (Twitter sentiment tracking)
- **Legal Document Analysis** (Extracting clauses from contracts)

---

# Natural Language Generation (NLG)

## Definition
NLG is the process where machines generate human-like text from structured data or other inputs.

## Stages of NLG
1. **Content Determination** (What to say?)
2. **Text Structuring** (Logical flow)
3. **Sentence Aggregation** (Combining related info)
4. **Lexicalization** (Choosing words)
5. **Referring Expression Generation** (Using pronouns like "it")
6. **Linguistic Realization** (Grammar & syntax)

## Types of NLG

| Type                   | Example                                                                      |
|------------------------|------------------------------------------------------------------------------|
| **Template-Based**     | Fill-in-the-blank ("Your order #123 is shipped.")                           |
| **Rule-Based**         | IF-THEN logic ("If temperature >30°C, say 'It’s hot.'")                    |
| **Machine Learning-Based** | GPT-3 generating creative stories.                                       |

## Applications of NLG
- **Automated Journalism** (AP News robot writing earnings reports)
- **Chatbot Responses** ("Here’s your tracking link: [URL]")
- **Personalized Emails** (Marketing campaigns)
- **Medical Reports** (Summarizing patient data)

---

# NLP vs. NLU vs. NLG: Key Differences

| Feature                | NLP                     | NLU                     | NLG                     |
|------------------------|-------------------------|-------------------------|-------------------------|
| **Purpose**            | Process & analyze text | Understand meaning      | Generate text           |
| **Input**              | Raw text               | Text + Context          | Data (tables, keywords) |
| **Output**             | Tokens, tags, entities | Intent, sentiment       | Human-like sentences    |
| **Example**            | POS tagging in a sentence | Detecting sarcasm in a tweet | GPT-3 writing an essay |

---

# Combined Workflow: NLP + NLU + NLG

### Example: Weather Chatbot
1. **NLP (Processing Input)**  
     User says: "Will it rain in Berlin tomorrow?"  
     - **Tokenization**: ["Will", "it", "rain", "in", "Berlin", "tomorrow", "?"]  
     - **POS Tagging**: ["Will" (verb), "Berlin" (noun)]

2. **NLU (Understanding Intent)**  
     - **Intent**: check_weather  
     - **Entities**: location=Berlin, date=tomorrow

3. **NLG (Generating Response)**  
     - **Data**: `{ "Berlin": { "weather": "rainy", "temp": "14°C" } }`  
     - **Output**: "Yes, it will rain tomorrow in Berlin (14°C)."

---

# Advanced Use Cases

### Healthcare
- **NLP**: Extract symptoms from patient notes.
- **NLU**: Diagnose possible illnesses.
- **NLG**: Generate treatment summaries.

### E-Commerce
- **NLP**: Analyze product reviews.
- **NLU**: Detect if a review says, "Battery life is poor."
- **NLG**: Auto-reply: "We’re sorry! Here’s a discount for your next purchase."

### Autonomous Vehicles
- **NLP**: Process voice commands ("Navigate to Starbucks").
- **NLU**: Resolve ambiguity ("Which Starbucks? There are 3 nearby.").
- **NLG**: Respond: "Taking you to the nearest Starbucks on Main St."

---

# Tools & Frameworks

| Task   | Tools                                                                 |
|--------|----------------------------------------------------------------------|
| **NLP** | NLTK, SpaCy, Stanford NLP                                           |
| **NLU** | Rasa, Dialogflow, LUIS (Microsoft)                                  |
| **NLG** | GPT-3, Hugging Face Transformers, Markov Chains                     |

---

# Future Trends
- **Multimodal NLP** (Combining text + images/video).
- **Zero-Shot Learning** (Models understanding tasks without training).
- **Ethical AI** (Reducing bias in language models).

---

# Final Thoughts
- **NLP** = "Reading" text.
- **NLU** = "Understanding" text.
- **NLG** = "Writing" text.