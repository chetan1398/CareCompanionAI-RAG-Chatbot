# CareCompanionAI-RAG-Chatbot

### Authors
 1. Chetan Warad - NUID: 002817179
 2. Nitish Belagali - NUID: 002645514
 3. Pavan Pai - NUID: 02833362


## About
This project is the final submission for the course Prompt Engineering INFO7375 at Northeastern University, conducted under the guidance of Professor Nick Brown. The project showcases the practical application of advanced prompt engineering techniques, LLMs, and generative AI to solve real-world problems in the healthcare domain.

### Video
[Link](https://drive.google.com/drive/folders/14OGm_O4LkL8ukeayPCR0S6aCbnRedwZF?usp=sharing)

### Project Setup
1. Set up a Neo4J AuraDB instace. 
2. Create a .env file with the following environment variables

```
NEO4J_URI=<YOUR_NEO4J_URI>
NEO4J_USERNAME=<YOUR_NEO4J_USERNAME>
NEO4J_PASSWORD=<YOUR_NEO4J_PASSWORD>

OPENAI_API_KEY=<YOUR_OPENAI_API_KEY>

HOSPITALS_CSV_PATH=/data/hospitals.csv
PAYERS_CSV_PATH=/data/payers.csv
PHYSICIANS_CSV_PATH=/data/physicians.csv
PATIENTS_CSV_PATH=/data/patients.csv
VISITS_CSV_PATH=/data/visits.csv
REVIEWS_CSV_PATH=/data/reviews.csv
EXAMPLE_CYPHER_CSV_PATH=/data/example_cypher.csv

CHATBOT_URL=http://host.docker.internal:8000/hospital-rag-agent

HOSPITAL_AGENT_MODEL=gpt-4o-mini
HOSPITAL_CYPHER_MODEL=gpt-4o-mini
HOSPITAL_QA_MODEL=gpt-4o-mini

NEO4J_CYPHER_EXAMPLES_INDEX_NAME=questions
NEO4J_CYPHER_EXAMPLES_NODE_NAME=Question
NEO4J_CYPHER_EXAMPLES_TEXT_NODE_PROPERTY=question
NEO4J_CYPHER_EXAMPLES_METADATA_NAME=cypher
```

3. Install Docker Compose
4. Open a terminal and run 
   ``` docker-compose up --build ```

5. After the container finishes building, you will be able to access the application at http://localhost:8501/

### Fine Tuning
1. **Fine-Tuning Process:** The fine-tuning process was crucial in enhancing the chatbot's performance. Below are the key steps and considerations taken:
2. **Data Collection:** Gathered diverse and representative question-answer pairs related to hospital management. The dataset was stored in a JSON file (fine_tuning_data.json) containing prompts and corresponding responses.
3. **Training Data Preparation:** Converted the raw data into a format suitable for fine-tuning, with prompt and completion keys.
4. **Prompt Engineering:** Developed a specific prompt template emphasizing the chatbot's role as a hospital management assistant.The template ensured that responses were contextually relevant and accurate.
5. **Model Selection:** Utilized the text-davinci-003 model from OpenAI for fine-tuning, chosen for its balance of performance and efficiency.
6. **Iterative Fine-Tuning:** Ran multiple iterations of fine-tuning with the prepared dataset.
Each iteration was reviewed to ensure improvements in response accuracy and relevance.
7. **Memory Integration:** Incorporated ConversationBufferMemory to maintain context across interactions, enhancing the conversational experience.
8. **Testing and Validation:** Post fine-tuning, the model was rigorously tested with new queries to validate its performance.Adjustments were made based on testing feedback to optimize the final model.
9. **Deployment:** The fine-tuned model was integrated into the chatbot's architecture, improving its response quality and user experience.


### Key Features and Functionalities

-   **Intelligent Query Resolution:** The chatbot can efficiently answer complex queries related to hospital management, including information on physicians, patient records, hospital reviews, and visit history, leveraging Neo4j's graph database.
-   **Custom Cypher Queries:** Users can ask detailed questions requiring specific Cypher queries, with the chatbot dynamically generating these queries based on the context.
-   **Context-Aware Conversations:** The chatbot maintains context across interactions, ensuring coherent and relevant responses throughout a conversation.
-   **Data-Driven Insights:** The system provides data-driven recommendations and insights, helping hospital administrators make informed decisions.

### Challenges Faced and How They Were Overcome

-   **Neo4j Integration:** Integrating Neo4j with the LLM presented challenges, particularly in ensuring accurate Cypher query generation. This was addressed by iterative prompt engineering and model fine-tuning, improving the chatbot's ability to generate precise queries.
-   **Maintaining Context:** Ensuring the chatbot retained context over extended interactions was challenging. This was mitigated by incorporating ConversationBufferMemory, which helped maintain continuity in dialogues.
-   **Fine-Tuning for Specificity:** Tailoring the LLM to the hospital domain required fine-tuning with domain-specific data. The challenge of obtaining relevant data was overcome by creating custom datasets, which significantly enhanced the model's relevance and accuracy.

### Conclusion

The CareCompanion AI chatbot effectively combines large language models with specialized knowledge bases to provide context-aware solutions in healthcare. By integrating advanced prompt engineering techniques and Neo4j, it addresses complex hospital management queries, proving to be a valuable tool for healthcare professionals.

### Future Scope

-   **Knowledge Base Expansion:** Incorporate additional datasets covering more aspects of healthcare management.
-   **Multilingual Support:** Add multilingual capabilities to serve a broader audience.
-   **Enhanced AI Models:** Upgrade to advanced models with reinforcement learning for improved accuracy.
-   **Mobile Integration:** Develop a mobile version for greater accessibility.


### License 
This project is licensed under the MIT License. See the LICENSE file for details.

